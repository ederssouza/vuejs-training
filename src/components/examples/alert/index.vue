<template>
  <div v-if="visible" class="alert alert-warning alert-dismissible fade show" role="alert">
    <strong>Atenção:</strong> Lorem ipsum dolor sit amet consectetur adipisicing elit.
    <Button @close="handleVisibility" />
  </div>
</template>

<script>
import Button from './Button'

export default {
  name: 'Alert',
  components: {
    Button
  },
  data () {
    return {
      visible: true
    }
  },
  methods: {
    handleVisibility () {
      this.visible = false
    }
  }
}
</script>
