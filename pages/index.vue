<template>
  <v-layout column justify-center align-center>
    <v-card>
      <v-container>
        <v-row justify="space-between">
          <v-col>
            <ProfilePicture />
          </v-col>

          <v-col>
            <v-card-text class="headline">
              Hi :)
            </v-card-text>

            <v-card-title class="display-1">
              This is Kitty!
            </v-card-title>

            <v-card-text>
              <p>
                I just finished my course MEng Computing specialised in
                Artificial Intelligence, at Imperial College London.
              </p>

              <p>
                This website is still under 'construction', so it looks like a
                mess. But I promise I'm on it!! Just please give me time to add
                more interesting content ;)
              </p>
            </v-card-text>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
  </v-layout>
</template>

<script lang="ts">
import ProfilePicture from '~/components/ProfilePicture.vue'

export default {
  name: 'Index',
  components: {
    ProfilePicture
  }
}
</script>
