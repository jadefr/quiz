<template>
  <div id="app">
    <Header/>
    <b-container class="bv-example-row">
      <b-row>
        <b-col>
          <QuestionBox
            v-if="questions.length"
            :currentQuestion="questions[index]"
            :next="next"
            :increment="increment"
          />
        </b-col>
      </b-row>
    </b-container>

    <Footer
      :numCorrect="numCorrect"
      :numTotal="numTotal"
    />

  </div>
</template>

<script>
import Header from '../components/Header'
import QuestionBox from '../components/QuestionBox.vue'
import Footer from '../components/Footer.vue'

export default {
  name: 'Home',
  components: {
    Header,
    QuestionBox,
    Footer
  },
  data () {
    return {
      questions: [],
      index: 0,
      numCorrect: 0,
      numTotal: 0
    }
  },
  methods: {
    next () {
      this.index++
    },
    increment (isCorrect) {
      if (isCorrect) {
        this.numCorrect++
      }
      this.numTotal++
    }
  },
  mounted: function () {
    fetch('https://opentdb.com/api.php?amount=30&category=9&type=multiple', {
      method: 'get'
    })
      .then(response => {
        return response.json()
      })
      .then(jsonData => {
        this.questions = jsonData.results
      })
  }
}
</script>

<style lang="css" scoped>
  @media (min-width: 768px) {
    .bv-example-row {
      width: 540px;
    }
  }
</style>
