<template>
  <div>
    <button v-text="buttonText" class="btn btn-success btn-sm" />&nbsp;
    <button class="btn btn-primary btn-sm">{{ buttonText }}</button>
  </div>
</template>

<script>
export default {
  name: 'DirectiveVText',
  data () {
    return {
      buttonText: 'Botão'
    }
  }
}
</script>
