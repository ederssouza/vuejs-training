<template>
  <button class="btn btn-success" @click="handleClick">{{ buttonText }}</button>
</template>

<script>
export default {
  data () {
    return {
      buttonText: 'Clique aqui'
    }
  },

  methods: {
    handleClick () {
      this.buttonText = 'Clicou'
    }
  },

  beforeCreate () {
    console.log('beforeCreate', { buttonText: this.buttonText })
  },

  created () {
    console.log('created', { buttonText: this.buttonText })
  },

  beforeMount () {
    console.log('beforeMount', { buttonText: this.buttonText })
  },

  mounted () {
    console.log('mounted', { buttonText: this.buttonText })
  },

  beforeUpdate () {
    console.log('beforeUpdate', { buttonText: this.buttonText })
  },

  updated () {
    console.log('updated', { buttonText: this.buttonText })
  },

  beforeDestroy () {
    console.log('beforeDestroy', { buttonText: this.buttonText })
  },

  destroyed () {
    console.log('destroyed', { buttonText: this.buttonText })
  }
}
</script>
