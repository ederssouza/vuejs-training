<template>
  <div>
    <div>Total de items: {{ total }}</div>

    <ul>
      <li v-for="item in items" :key="item.id">
        {{ item.text }}
      </li>
    </ul>

    <div>
      Exibindo {{ pagination.firstItem }} / {{ pagination.totalItens }}
    </div>
  </div>
</template>

<script>
import moment from 'moment'

export default {
  name: 'List',
  props: {
    total: {
      type: Number,
      default: 0
    },
    items: {
      type: Array
    },
    pagination: {
      type: Object
    }
  },
  filters: {
    formatDate (date) {
      return moment(date).format('DD/MM/YYYY')
    }
  }
}
</script>
