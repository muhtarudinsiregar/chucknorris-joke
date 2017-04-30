<template>
  <div id="quote">
    <div class="container">
      <div class="jumbotron">
        <h2><span class="glyphicon glyphicon-list-alt"></span>&nbsp;Chuck Norris Joke</h2>
        <hr>
        <h3 class="text-center">
          {{ quote.joke }}
        </h3>
        <button type="button"  class="btn btn-primary" name="button" @click="getRandomQuote()">Get Random Joke</button>
      </div>
    </div>
  </div>
</template>

<script lang="">
export default {
  name: 'quotesComponent',
  data() {
    return {
      quotes: [],
      quote: '',
    };
  },
  methods: {
    getRandomQuote() {
      this.$http.get('http://api.icndb.com/jokes/random')
      .then((response) => {
        this.quote = response.data.value;
      });
    },
  },
  mounted() {
    this.getRandomQuote();
    setInterval(() => {
      this.getRandomQuote();
    }, 10000);
  },
  ready() {
    this.getRandomQuote();

    setInterval(() => {
      this.getRandomQuote();
    }, 1000);
  },
};
</script>
