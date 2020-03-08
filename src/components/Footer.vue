<template>
  <footer>
    <p>Counter: {{ numCorrect }} / {{ numTotal }} </p>
  </footer>
</template>

<script>
export default {
  props: [
    'numCorrect',
    'numTotal'
  ]
}
</script>

<style scoped>
  p {
    color: rgb(112, 114, 116);
  }
</style>
