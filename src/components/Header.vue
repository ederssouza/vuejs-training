<template>
  <nav class="navbar navbar-dark bg-success fixed-top">
    <div class="container">
      <a class="navbar-brand">
        Introdução ao Vue.js 2
      </a>
      <button
        v-if="routeName !== 'Home'"
        class="btn btn-light btn-sm my-2 my-sm-0"
        type="button"
        @click="$router.push({ name: 'Home' })"
      >
        Todos os exemplos
      </button>
    </div>
  </nav>
</template>

<script>
export default {
  computed: {
    routeName () {
      return this.$route.name
    }
  }
}
</script>
