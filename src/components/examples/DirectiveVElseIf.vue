<template>
  <div>
    <button
      class="btn btn-success btn-sm"
      @click="handleToggleLetter"
    >
      Alternar letra
    </button>

    <div class="mt-3">
      <div v-if="selectedLetter === 'A'">Letra A</div>
      <div v-else-if="selectedLetter === 'B'">Letra B</div>
      <div v-else-if="selectedLetter === 'C'">Letra C</div>
      <div v-else>Nenhuma letra</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DirectiveVElseIf',
  data () {
    return {
      letters: ['A', 'B', 'C'],
      selectedLetter: ''
    }
  },
  methods: {
    handleToggleLetter () {
      const dynamicIndex = Math.round(Math.random() * 3)
      this.selectedLetter = this.letters[dynamicIndex] || this.letters[0]
    }
  }
}
</script>
