
<template>
  <div id="app">
    <p>
      Question: <input v-model="question" />
    </p>
    <p>
      Answer: {{ answer }}
    </p>
    <p>
      <img v-if="image" :src="image">
    </p>
  </div>
</template>

<script>
  import { debounce } from 'lodash';
export default {
  name: "App",
  data() {
    return {
      question: '',
      answer: 'Please ask me a question...',
      image: null,
    }
  },
  created() {
    this.getAnswerDebounced = debounce(this.getAnswer, 500);
  },
  watch: {
    question(newValue, oldValue) {
      console.log({ newValue, oldValue });

      this.getAnswerDebounced();
    }
  },
  methods: {
    getAnswer() {
      if(this.question.indexOf('?') === -1) {
        this.answer = 'Put a question mark in your question';
        return;
      }

      fetch('https://yesno.wtf/api')
        .then(response => {
          response.json().then(data => {
            this.answer = data.answer;
            this.image = data.image;
          })
        })
        .catch(error => {
          this.answer = 'Something went wrong '+error;
        })
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
