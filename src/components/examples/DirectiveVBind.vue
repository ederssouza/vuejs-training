<template>
  <div>
    <button
      :title="buttonText"
      :style="{ 'font-size': fontSize + 'px' }"
      class="btn btn-success"
      :class="{ 'btn-sm': small }"
    >
      {{ buttonText }}
    </button>
  </div>
</template>

<script>
export default {
  name: 'DirectiveVBind',
  data () {
    return {
      buttonText: 'Button text',
      small: true,
      fontSize: 10
    }
  }
}
</script>
