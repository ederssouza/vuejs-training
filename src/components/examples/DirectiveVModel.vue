<template>
  <div>
    <input v-model="input" type="text" class="form-control">
    {{ input }}
  </div>
</template>

<script>
export default {
  name: 'DirectiveVModel',
  data () {
    return {
      input: ''
    }
  }
}
</script>
