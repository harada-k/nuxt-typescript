<template>
  <div class="container">
    <div>
      <logo :counter="counter" />
      <h1 class="title">
        nuxt-typescript
      </h1>
      <h2 class="subtitle">
        My impressive Nuxt.js project
      </h2>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          class="button--green"
        >
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
      <div class="actions">
        <a class="button--action" @click="addTada">🎉 {{ tada }}</a>
        <a class="button--action" @click="addSparkles">✨ {{ sparkles }}</a>
        <a class="button--action" @click="addThumbsup">👍 {{ thumbsup }}</a>
        <a class="button--action" @click="addHeart">🧡 {{ heart }}</a>
        <a class="button--grey" @click="clear">Clear</a>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Logo from '~/components/Logo.vue'

export default Vue.extend({
  components: {
    Logo
  },
  data () {
    return {
      tada: 0,
      sparkles: 0,
      thumbsup: 0,
      heart: 0
    }
  },
  computed: {
    counter (): number {
      return this.tada + this.sparkles + this.thumbsup + this.heart
    }
  },
  methods: {
    addTada (): void {
      this.tada++
    },
    addSparkles (): void {
      this.sparkles++
    },
    addThumbsup (): void {
      this.thumbsup++
    },
    addHeart (): void {
      this.heart++
    },
    clear (): void {
      this.tada = 0
      this.sparkles = 0
      this.thumbsup = 0
      this.heart = 0
    }
  }
})
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

.actions {
  margin-top: 15px;
}

.button--action {
  border: 1px solid #35495e;
  border-radius: 4px;
  display: inline-block;
  padding: 6px 16px;
  margin-left: 15px;
  vertical-align: middle;
}
</style>
