<template>
  <div>
    <div class="bk-container">
      <v-img class="bk" :src="mattKittyPic"/>
      <div class="title-text-box">
        <div class="main-text">Matthew & Kexin</div>
        <div class="sub-text">28 Aug, 2021</div>
      </div>
    </div>

    <div class="context-container">
      <v-container class="text-center">
        <h3 class="my-4">
          Please join our wedding ceremony at Christ Church Kensington,<br>
          on 28 Aug 2021 at 14:00 BST and 21:00 CST.<br> <br>
          Click the RSVP button to tell us that you are coming,<br>
          either in-person or virtually.
        </h3>

        <v-btn outlined class="rsvp-btn mt-2" v-on:click="rsvp">RSVP</v-btn>
      </v-container>
    </div>
  </div>
</template>

<script lang="ts">
const rsvpForm = 'https://forms.gle/mWKz5wbeXkHvFBzN6'

export default {
  name: "matt-kitty-wedding",
  layout: "wedding",
  data() {
    return {
      mattKittyPic: require('~/static/IMG_5951.jpeg')
    }
  },
  methods: {
    rsvp: function() {
      window.open(rsvpForm)
    }
  }
}
</script>

<style scoped>

.bk-container {
  position: relative;
  width: 100%;
}

.title-text-box {
  position: absolute;
  font-family: 'Montserrat', sans-serif;
  font-weight: bold;
  z-index: 100;
  top: 150px;
  left: 20%;
  text-align: center;
}

.main-text {
  font-size: 50px;
}

.sub-text {
  font-size: 35px;
}

.context-container {
  position: relative;
  width: 100%;
  font-family: 'Montserrat', sans-serif;
  margin-top: 20px;
}

.rsvp-btn {
  font-size: 35px;
}

</style>

