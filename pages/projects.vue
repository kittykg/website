<template>
  <v-layout column justify-center align-center>
    <v-container>
      <v-col>
        <v-card v-for="project in projects" class="ma-2">
          <v-card-title>
            <v-btn :href="project.link" icon target="_blank">
              <v-icon>mdi-{{ project.github ? 'github' : 'gitlab' }}</v-icon>
            </v-btn>{{ project.title }}
          </v-card-title>

          <v-card-subtitle>{{ project.subtitle }}</v-card-subtitle>
        </v-card>
      </v-col>
    </v-container>
  </v-layout>
</template>

<script lang="ts">
export default {
  name: 'Projects',
  data: () => {
    return {
      projects: [
        {
          title: 'Tamagucci',
          github: true,
          link: 'https://github.com/ichack20-pet-drone/droneboy',
          subtitle: 'ICHack20 Best Entertainment Hack Winner'
        },
        {
          title: 'Drone Playground',
          github: true,
          link: 'https://github.com/xDrone-DSL',
          subtitle: '3rd Year Group Project'
        },
        {
          title: 'SpeedBoards',
          github: false,
          link: 'https://gitlab.doc.ic.ac.uk/kg3217/keyboardBundle',
          subtitle: 'ICHack19 Best Native Hack Runner Up'
        }
      ]
    }
  }
}
</script>
