<template>
  <v-app>
    <v-app-bar absolute elevation="0" color="transparent">
      <v-toolbar-title class="bar-title">Matt & Kitty</v-toolbar-title>
      <v-spacer />
      <v-btn plain tile text class="bar-buttons">Wedding</v-btn>
      <v-btn plain tile text class="bar-buttons">Gifts</v-btn>
    </v-app-bar>

    <v-content>
        <nuxt />
    </v-content>
  </v-app>
</template>

<script lang="ts">
export default {
  name: "wedding",
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');

.bar-title {
  font-family: 'Montserrat', sans-serif;
  font-size: 34px;
  padding-left: 30px;
  font-weight: bold;
}

.bar-buttons {
  font-size: 20px;
}

</style>
