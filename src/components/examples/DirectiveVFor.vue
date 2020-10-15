<template>
  <div>
    <div v-for="item in array" :key="item.text">
      {{ item.text }}
    </div>

    <hr />

    <div v-for="item in object" :key="item">
      {{ item }}
    </div>

    <hr />

    <div v-for="number in 4" :key="number">
      {{ number }}
    </div>

    <hr />

    <div v-for="letter in  string" :key="letter">
      {{ letter }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'DirectiveVFor',
  data () {
    return {
      array: [
        { text: 'JavaScript' },
        { text: 'CSS3' },
        { text: 'HTML5' },
        { text: 'Vue.js' }
      ],
      object: {
        lang1: 'Java',
        lang2: 'C#',
        lang3: 'Node.js'
      },
      string: 'Vue.js'
    }
  }
}
</script>
