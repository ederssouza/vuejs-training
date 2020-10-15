<template>
  <div
    class="alert"
    :class="[
      { 'alert-success': kind === 'success' },
      { 'alert-danger': kind === 'danger' },
      { 'alert-warning': kind === 'warning' },
      { 'alert-info': kind === 'info' }
    ]"
    role="alert"
  >
    <span v-html="message" />
    <button
      v-if="close"
      type="button"
      class="close"
      data-dismiss="alert"
      aria-label="Close"
      @click="handleClick"
    >
      <span aria-hidden="true">&times;</span>
    </button>
  </div>
</template>

<script>
export default {
  name: 'Alert',
  props: {
    kind: {
      type: String,
      default: 'success'
    },
    message: {
      type: String,
      required: true
    },
    close: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    handleClick () {
      console.log('handleClick')
    }
  }
}
</script>
