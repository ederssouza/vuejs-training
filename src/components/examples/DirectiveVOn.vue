<template>
  <div>
    <button class="btn btn-success btn-sm" @click="handleClick">Evento de click</button>
    &nbsp;
    <button class="btn btn-primary btn-sm" @mouseenter="handleMouseEnter">Evento de mouseenter</button>
  </div>
</template>

<script>
export default {
  name: 'DirectiveVOn',
  data () {
    return {}
  },
  methods: {
    handleClick () {
      console.log('handleClick')
    },

    handleMouseEnter () {
      console.log('handleMouseEnter')
    }
  }
}
</script>
