<template>
  <div class="text-center" dark :color="contact.normalColor">
    <v-btn
      rounded
      :href="(contact.name === 'Email' ? 'mailto:' : '') + this.contact.link"
      :target="contact.name === 'Email' ? '' : '_blank'"
      style="text-decoration: none;"
    >
      {{ contact.info }}
    </v-btn>
  </div>
</template>

<script lang="ts">
import { PropType } from "vue";

interface Contact {
  name: string;
  icon: string;
  activeColor?: string;
  normalColor?: string;
  info: string;
  link?: string;
}

export default {
  name: "ContactExpandCard",
  props: {
    contact: { type: Object as PropType<Contact>, required: true },
  }
};
</script>
