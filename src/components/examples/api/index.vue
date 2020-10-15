<template>
  <div>
    <Table v-if="currentStatus === 'success'" :users="users" />

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

export default {
  name: 'Api',
  components: {
    Table
  },
  data () {
    return {
      users: [],
      currentStatus: ''
    }
  },
  methods: {
    async loadData () {
      this.currentStatus = 'loading'

      try {
        const { data: res } = await axios.get('https://nodejs-mock-server.herokuapp.com/users')
        this.users = res && Array.isArray(res.data) ? [...res.data] : []
        this.currentStatus = 'success'
      } catch (error) {
        console.log(error)
        this.currentStatus = 'error'
      }
    }
  },
  mounted () {
    this.loadData()
  }
}
</script>
