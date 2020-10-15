<template>
  <div>
    <div class="form-group">
      <button
        class="btn btn-success"
        @click="handleClickButton"
      >
        {{ buttonText }}
      </button>
    </div>

    <div class="form-group">
      <input
        type="text"
        class="form-control"
        @focus="handleFocus"
        @blur="handleBlur"
        @input="handleInput"
      >
    </div>

    <a href="#" @click.prevent="handleClickLink">{{ linkText }}</a>
  </div>
</template>

<script>
export default {
  name: 'Methods',
  data () {
    return {
      buttonText: '',
      linkText: 'Link'
    }
  },
  methods: {
    loadDefaultText () {
      this.buttonText = 'Botão'
    },

    handleClickButton () {
      this.buttonText = 'Outro texto'
    },

    handleInput (event) {
      const val = event.target.value
      console.log('handleInput', val)
    },

    handleFocus () {
      console.log('handleFocus')
    },

    handleBlur () {
      console.log('handleBlur')
    },

    handleClickLink () {
      this.linkText = 'Outro link'
    }
  },
  mounted () {
    this.loadDefaultText()
  }
}
</script>
