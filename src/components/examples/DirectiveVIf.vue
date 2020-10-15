<template>
  <div>
    <button
      class="btn btn-success btn-sm"
      @click="visible = !visible"
    >
      {{ visible ? 'Ocultar texto' : 'Exibir texto' }}
    </button>

    <div v-if="visible" class="mt-3">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Dicta excepturi numquam, adipisci alias ullam facere eum quasi nam. Ut amet doloribus, deleniti omnis reiciendis tempora deserunt voluptatibus? Tempora, fuga eaque.</div>
  </div>
</template>

<script>
export default {
  name: 'DirectiveVIf',
  data () {
    return {
      visible: true
    }
  }
}
</script>
