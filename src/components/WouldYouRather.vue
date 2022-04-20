<template>
  <div class="wyr">
   
   <h2><i>Please make your choice!</i></h2>
   <h3>{{ question }}</h3>
<br>
   <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change="choiceMade">
   <label>{{ answer1 }} </label>

   <input type="radio" v-model="choice" v-bind:value="answer2" v-on:change="choiceMade">
   <label>{{ answer2 }} </label>

  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    question: String,
    answer1: String,
    answer2: String,
  },
  data() {
    return {
      choice: ''
    }
  }, 
  methods: {
    choiceMade() {
      this.$emit('answer-changed', this.choice)
     // console.log('choice!')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h2 {
  background: rgb(214, 13, 13);
  color: #000;
}
h3 {
  border: 1px;
  background:rgb(255, 58, 58);
  margin: 40px 0 0;
  color:rgb(7, 7, 7); 
}


.wyr { /*adding styles*/
  margin: 10px;
  border: 2px rgba(0, 0, 0, 0);
  background: rgb(43, 44, 42);
}

</style>
