<template>
  <div id="quote">
    <div class="container">
      <div class="">
        <div class="row">
          <div class="col-md-8 offset-md-2">
            <div class="quote"><i class="fa fa-quote-left fa-4x"></i></div>

            <blockquote class="text-center joke-content">
              <p>{{ quote.joke }}</p>
            </blockquote>

            <blockquote>
              <p class="joke-content">- Chuck norris joke number {{ quote.id }}</p>
            </blockquote>

            <br>

            <a href="http://www.icndb.com/" target="_blank" class="source">Source: http://www.icndb.com/</a>
          </div>
        </div>

        <!-- <button type="button"  class="btn btn-primary btn-margin" name="button" @click="getRandomQuote()">Get Random Joke</button> -->
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
      this.$http.get('http://api.icndb.com/jokes/random?escape=javascript')
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
};
</script>

<style scoped>
.quote {
    color: rgba(0,0,0,.1);
    text-align: center;
    margin-bottom: 30px;
}

.joke-content {
  font-family: 'PT Mono', monospace;
  font-size: 24px;
}
</style>
