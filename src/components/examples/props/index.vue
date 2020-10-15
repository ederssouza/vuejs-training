<template>
  <div>
    <Alert kind="info" message="Minha mensagem" close />
    <hr>
    <List :total="items.length" :items="items" :pagination="pagination" />
  </div>
</template>

<script>
import Alert from './Alert'
import List from './List'

export default {
  name: 'Props',
  components: {
    Alert,
    List
  },
  data () {
    return {
      items: [
        { id: 1, text: 'Item 1' },
        { id: 2, text: 'Item 2' },
        { id: 3, text: 'Item 3' },
        { id: 4, text: 'Item 4' }
      ],
      pagination: {
        firstItem: 1,
        totalItens: 20
      }
    }
  }
}
</script>
