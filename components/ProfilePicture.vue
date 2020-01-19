<template>
  <v-img :src="profilePic" eager max-width="500" />
</template>

<script lang="ts">
export default {
  name: 'ProfilePicture',
  data () {
    return {
      profilePic: require('~/static/profile_pic.jpg')
    }
  }
}
</script>
