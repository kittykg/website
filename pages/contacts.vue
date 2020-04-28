<template>
  <v-sheet class="mx-auto" elevation="8" max-width="80%">
    <v-slide-group v-model="model" class="pa-4" show-arrows center-active>
      <v-slide-item
        v-for="contact in contacts"
        v-bind:key="contact.name"
        v-slot:default="{ active, toggle }"
      >
        <v-card
          :color="active ? contact.activeColor : contact.normalColor"
          @click="toggle"
          class="ma-4"
          align="center"
          justify="center"
          width="200"
        >
          <v-card-title>
            {{ contact.name }}
          </v-card-title>
          <v-card-title>
            <v-icon>{{ contact.icon }}</v-icon>
          </v-card-title>
        </v-card>
      </v-slide-item>
    </v-slide-group>

    <v-expand-transition>
      <v-sheet v-if="model != null" height="200">
        <v-row class="fill-height" align="center" justify="center">
          <ContactExpandCard :contact="contacts[model]" />
        </v-row>
      </v-sheet>
    </v-expand-transition>
  </v-sheet>
</template>

<script lang="ts">
import ContactExpandCard from "~/components/ContactExpandCard.vue";
export default {
  name: "Contacts",
  components: { ContactExpandCard },
  data() {
    return {
      model: null,
      contacts: [
        {
          name: "Email",
          icon: "mdi-email",
          activeColor: "red darken-4",
          normalColor: "red lighten-3",
          info: "Gmail",
          link: "kexinkittygu@gmail.com",
        },
        {
          name: "GitHub",
          icon: "mdi-github",
          activeColor: "grey darken-4",
          normalColor: "grey lighten-2",
          info: "kittykg",
          link: "https://github.com/kittykg",
        },
        {
          name: "Facebook",
          icon: "mdi-facebook",
          activeColor: "blue darken-2",
          normalColor: "blue lighten-3",
          info: "Kexin Gu",
          link: "https://www.facebook.com/kitty.gu.9047",
        },
        {
          name: "Instagram",
          icon: "mdi-instagram",
          activeColor: "pink darken-4",
          normalColor: "pink lighten-3",
          info: "kitty128",
          link: "https://www.instagram.com/kittygu128/",
        },
        {
          name: "Twitter",
          icon: "mdi-twitter",
          activeColor: "blue darken-4",
          normalColor: "blue lighten-3",
          info: "kittykexin",
          link: "https://twitter.com/kittykexin",
        },
        {
          name: "LinkedIn",
          icon: "mdi-linkedin",
          activeColor: "cyan darken-3",
          normalColor: "cyan lighten-4",
          info: "Kexin Gu",
          link: "https://www.linkedin.com/in/kexin-gu-9a0296151/",
        },
      ],
    };
  },
};
</script>
