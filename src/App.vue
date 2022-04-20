<template>

  <div id="app"> 

  <h1> Would You Rather...</h1>

  <would-you-rather v-bind:question="wyrQuestion" 
  v-bind:answer1="wyrAnswer1"
  v-bind:answer2="wyrAnswer2"
  v-on:answer-changed="answerChanged"></would-you-rather>  <!--template has its own vueapp-->

<p>{{ userSelectionMessage }} </p>
  </div>
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data() {
    return {
      wyrQuestion: 'Would you rather be five years younger or five years older?',
      wyrAnswer1: 'Younger',
      wyrAnswer2: 'Older',
      userSelectionMessage: ''
    }
  },
  methods: {
    answerChanged(choice) {
      this.userSelectionMessage = `Prepare to be five years ${choice}!`
    }
  }
}
</script>

<style>

body {
  background: #fa4134;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  margin-top: 60px;
  background:#b30707;
}
</style>
