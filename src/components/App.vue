<template>
  <div id="app">
    <h3>
      Got jokes?
    </h3>
    <button class="btn btn-primary"
            @click="initJokes">
      Add ten random Jokes
    </button>
    <button class="btn btn-primary"
            @click="addJoke">
      Add random Joke
    </button>
    <div class="col-md-12">
      <joke-block v-for="(joke, index) in $store.state.jokes"
                  :joke="joke"
                  key="joke">
      </joke-block>
    </div>
  </div>
</template>

<script>
  import JokeBlock from './Joke.vue'
  import { mapActions } from 'vuex'

  export default {
    components: {
      JokeBlock
    },
    methods: mapActions([
      'initJokes',
      'addJoke'
    ])
  }
</script>
