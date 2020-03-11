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
  footer {
    padding: 1em 0;
  }

  p {
    /*color: rgb(112, 114, 116);*/
    color: white;
  }
</style>
