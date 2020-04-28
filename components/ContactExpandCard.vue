<template>
  <div class="text-center">
    <v-btn
      rounded
      :color="contact.activeColor"
      :href="(contact.name === 'Email' ? 'mailto:' : '') + this.contact.link"
      :target="contact.name === 'Email' ? '' : '_blank'"
      style="text-decoration: none;"
    >
      <v-icon class="pr-2">{{ contact.icon }}</v-icon>
      <v-spacer />
      {{ contact.info }}
    </v-btn>
  </div>
</template>

<script lang="ts">
import { PropType } from "vue";

interface Contact {
  name: string;
  icon: string;
  activeColor: string;
  normalColor?: string;
  info: string;
  link?: string;
}

export default {
  name: "ContactExpandCard",
  props: {
    contact: { type: Object as PropType<Contact>, required: true },
  },
};
</script>
