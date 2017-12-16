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
    <div>
      <span v-for="type in types">
        <input type="checkbox"
               :value="type"
               v-model="checkedTypes"
               checked>
        <label>{{ type }}</label>&nbsp;
      </span>
    </div>
    <div class="col-md-12">
      <joke-block v-for="(joke, index) in $store.state.jokes"
                  v-show="checkedTypes.includes(joke.type)"
                  :joke="joke"
                  :index="index"
                  key="joke">
      </joke-block>
    </div>
  </div>
</template>

<script>
  import JokeBlock from './Joke.vue'
  import { mapActions } from 'vuex'

  export default {
    data () {
      return {
        types: [
          'general', 'knock-knock', 'programming'
        ],
        checkedTypes: [
          'general', 'knock-knock', 'programming'
        ]

      }
    },
    components: {
      JokeBlock
    },
    methods: mapActions([
      'initJokes',
      'addJoke'
    ])
  }
</script>
