<template>
  <div class="col-md-6">
    <div class="joke-card">
      <div class="cad-block">
        <button @click="removeJoke(index)"
                class="close">
          <span>&times;</span>
        </button>
        <p><u>{{ joke.setup }}</u></p>
        <p><em>{{ joke.punchline }}</em></p>
      </div>
    </div>
  </div>
</template>

<script>
  import { mapActions } from 'vuex'

  export default {
    props: {
      joke: {},
      index: Number
    },
    methods: mapActions([
      'removeJoke'
    ])
  }
</script>
