<template>
  <button v-html="buttonHTML" class="btn btn-success btn-sm" />
</template>

<script>
export default {
  name: 'DirectiveVHtml',
  data () {
    return {
      buttonHTML: 'Botão <strong>HTML</strong>'
    }
  }
}
</script>
