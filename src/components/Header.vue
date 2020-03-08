<template>
  <div>
    <header>
      <p>Quiz</p>
    </header>

  </div>
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
  header {
    color: rgb(112, 114, 116);
    font-size: 2rem;
    line-height: 2rem;
    margin-top: 20px;
  }
</style>
