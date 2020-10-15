<template>
  <div>
    <button
      class="btn btn-success btn-sm"
      @click="visible = !visible"
    >
      Toggle text
    </button>

    <div class="mt-3">
      {{ visible ? 'Text 1' : 'Text 2' }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'DirectiveVElse',
  data () {
    return {
      visible: true
    }
  }
}
</script>
