<template>
  <a v-on:click="play_next" :disabled="disabled">
    <span class="icon"><i class="mdi mdi-skip-forward"></i></span>
  </a>
</template>

<script>
import webapi from '@/webapi'

export default {
  name: 'PlayerButtonNext',

  computed: {
    disabled () {
      return !this.$store.state.queue || this.$store.state.queue.count <= 0
    }
  },

  methods: {
    play_next: function () {
      if (this.disabled) {
        return
      }

      webapi.player_next()
    }
  }
}
</script>

<style>
</style>
