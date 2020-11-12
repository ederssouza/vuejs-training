<template>
  <div>
    <div v-if="currentStatus === 'success'">
      <Table :users="users" />
      <Paginator
        :totalPages="paginator.totalPages"
        :currentPage="paginator.page"
        @update="handlePagination"
      />
    </div>

    <div v-if="currentStatus === 'error'">
      Ocorreu um erro
    </div>

    <div v-if="currentStatus === 'loading'">
      Carregando...
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import Table from './Table'
import Paginator from './Paginator'

export default {
  name: 'Api',
  components: {
    Table,
    Paginator
  },
  data () {
    return {
      users: [],
      currentStatus: '',
      paginator: {
        page: 1,
        limit: 2,
        totalPages: 0
      }
    }
  },
  methods: {
    handlePagination (page) {
      this.paginator = {
        ...this.paginator,
        page
      }

      // this.loadData()
    },

    async loadData () {
      this.currentStatus = 'loading'

      try {
        const { page, limit } = this.paginator
        const { data: res } = await axios.get('https://nodejs-mock-server.herokuapp.com/users', {
          params: { page, limit }
        })

        if (res) {
          this.users = [...res.data]
          this.paginator = {
            ...this.paginator,
            totalPages: res.totalPages
          }
        }

        this.currentStatus = 'success'
      } catch (error) {
        console.log(error)
        this.currentStatus = 'error'
      }
    }
  },
  watch: {
    'paginator.page' (newValue, oldValue) {
      this.loadData()
    }
  },
  mounted () {
    this.loadData()
  }
}
</script>
