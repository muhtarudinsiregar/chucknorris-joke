<template>
  <div id="quote">
    <div>
      <div class="jumbotron">
        <h2><span class="glyphicon glyphicon-list-alt"></span>&nbsp;Chuck Norris Quotes</h2>
        <h1>
          {{ quote.joke }}
        </h1>
        <h3>&quot; Ntaknces</h3>
        <button type="button" name="button" @click="getRandomQuote()">Get Random Quotes</button>
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
  },
};
</script>
