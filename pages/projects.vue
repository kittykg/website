<template>
  <v-layout column justify-center align-center>
    <v-container>
      <v-col>
        <v-card
          v-for="project in projects"
          v-bind:key="project.title"
          class="ma-2"
        >
          <v-card-title>
            <v-btn :href="project.link" icon target="_blank">
              <v-icon
                >mdi-{{ project.github ? "github" : "gitlab" }}</v-icon
              > </v-btn
            >{{ project.title }}
          </v-card-title>

          <v-card-subtitle>{{ project.subtitle }}</v-card-subtitle>
        </v-card>
      </v-col>
    </v-container>
  </v-layout>
</template>

<script lang="ts">
export default {
  name: "Projects",
  data: () => {
    return {
      projects: [
        {
          title: "HACR - Hybrid Architecture for Concept Reasoning",
          github: true,
          link: "https://github.com/kittykg/hacr",
          subtitle: "Final Year Individual Project at Imperial"
        },
        {
          title: "Tamagucci",
          github: true,
          link: "https://github.com/ichack20-pet-drone/droneboy",
          subtitle: "ICHack20 Best Entertainment Hack Winner",
        },
        {
          title: "Drone Playground",
          github: true,
          link: "https://github.com/xDrone-DSL",
          subtitle: "3rd Year Group Project",
        },
        {
          title: "SpeedBoards",
          github: false,
          link: "https://gitlab.doc.ic.ac.uk/kg3217/keyboardBundle",
          subtitle: "ICHack19 Best Native Hack Runner Up",
        },
        {
          title: "Film Pudding",
          github: true,
          link: "https://github.com/kittykg/film-pudding",
          subtitle: "A machine learning model to predict my rating of films."
        }
      ],
    };
  },
};
</script>
