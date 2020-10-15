<template>
  <button
    type="button"
    class="close"
    data-dismiss="alert"
    aria-label="Close"
    @click="close"
  >
    <span aria-hidden="true">&times;</span>
  </button>
</template>

<script>
export default {
  name: 'Button',
  methods: {
    close () {
      this.$emit('close')
    }
  }
}
</script>
