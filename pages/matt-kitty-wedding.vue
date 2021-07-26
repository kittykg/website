<template>
  <v-container class="text-center">
    <h3 class="my-4">
      Please join our wedding ceremony at Christ Church Kensington,<br>
      on 28 Aug 2021 14:00 BST, 21:00 CST.<br> <br>
      Click the RSVP button to tell us that you would like to come,<br>
      either in-person or virtually.
    </h3>

    <v-btn outlined class="rsvp-btn my-2" v-on:click="rsvp">RSVP</v-btn>

    <h3 class="my-4">
      If you'd like to give us a small gift, please check out the list
      <a href="/wedding-gift-list">here</a>.
    </h3>
  </v-container>
</template>

<script lang="ts">
const rsvpForm = 'https://forms.gle/mWKz5wbeXkHvFBzN6'

export default {
  name: "matt-kitty-wedding",
  layout: "wedding",
  methods: {
    rsvp: function () {
      window.open(rsvpForm)
    }
  }
}
</script>

<style scoped>

.rsvp-btn {
  font-size: 35px;
}

</style>

