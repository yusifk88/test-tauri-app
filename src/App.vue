<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import Greet from "./components/Greet.vue";
import TestPluginsComponent from "./components/TestPluginsComponent.vue";
</script>

<template>
<v-app>
  <v-container>
    <v-btn color="blue" variant="flat" size="x-large" rounded block> Welcome to my desktop app </v-btn>


    <v-card>
      <v-card-title>Hey and this a vuetify card</v-card-title>
      <v-card-text>
        <h2>And some details here <v-icon>mdi-home</v-icon></h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Labore laborum officia quas reiciendis rerum saepe sapiente similique sint tempore, veniam? Accusamus cumque deserunt earum expedita, facere quam quidem. Consequuntur, debitis.
        </p>
      </v-card-text>
    </v-card>

    <test-plugins-component></test-plugins-component>
  </v-container>
</v-app>
</template>



<style scoped>
.logo.vite:hover {
  filter: drop-shadow(0 0 2em #747bff);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #249b73);
}
</style>
