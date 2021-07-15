<template>
  <v-app class="wedding-app">
    <v-app-bar absolute elevation="0" color="transparent">
      <v-toolbar-title class="bar-title">Matt & Kitty</v-toolbar-title>
      <v-spacer/>
      <div v-for="page in weddingPages">
        <v-btn class="bar-buttons"
               plain tile text router :to="page.path">
          {{ page.title }}
        </v-btn>
      </div>
    </v-app-bar>

    <v-main>
      <div class="bk-container">
        <v-img class="bk" :src="bkImg"/>
        <div class="title-text-box" v-bind:class="textBoxClass">
          <div class="main-text">{{ mainText }}</div>
          <div class="sub-text">{{ subText }}</div>
        </div>
      </div>
      <div class="context-container my-6">
        <nuxt/>
      </div>
    </v-main>

    <v-bottom-navigation horizontal>
      <v-btn href="mailto:matthew.kexin@gmail.com">
        <span>Contact us</span>
        <v-icon>mdi-email</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue'

const weddingPagePath = '/matt-kitty-wedding'
const giftsPagePath = '/wedding-gift-list'

export default Vue.extend({
  name: "wedding",
  data() {
    return {
      weddingPages: [
        {
          title: 'Wedding',
          path: weddingPagePath
        },
        {
          title: 'Gifts',
          path: giftsPagePath
        }
      ]
    }
  },
  computed: {
    isWeddingPage: function () : boolean {
      return this.$route.path == weddingPagePath
    },
    textBoxClass: function() {
      return {
        'ttb-wedding': this.$route.path == weddingPagePath,
        'ttb-gifts': this.$route.path == giftsPagePath
      }
    },
    bkImg: function () {
      if (this.isWeddingPage)
        return require('~/static/wedding-page-img.jpeg')
      return require('~/static/gifts-page-img.jpg')
    },
    mainText: function () : string {
      if (this.isWeddingPage)
        return 'Matthew & Kexin'
      return 'Gifts'
    },
    subText: function() : string {
      if (this.isWeddingPage)
        return '28 Aug, 2021'
      return 'Contribute to our gift list'
    }
  }
})

</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');

.wedding-app {
  font-family: 'Montserrat', sans-serif;
}

.bar-title {
  font-size: 34px;
  padding-left: 30px;
  font-weight: bold;
}

.bar-buttons {
  font-size: 20px;
}

.bk-container {
  position: relative;
  width: 100%;
}

.title-text-box {
  position: absolute;
  font-weight: bold;
  z-index: 100;
}

.ttb-wedding {
  text-align: center;
  top: 150px;
  left: 20%;
}

.ttb-gifts {
  text-align: left;
  bottom: 40%;
  left: 10%;
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
}

</style>
