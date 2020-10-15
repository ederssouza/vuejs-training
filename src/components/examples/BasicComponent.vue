<template>
  <button class="btn btn-success">{{ text }}</button>
</template>

<script>
export default {
  name: 'BasicComponent',
  data () {
    return {
      text: 'Botão'
    }
  }
}
</script>

<style scoped>
</style>
