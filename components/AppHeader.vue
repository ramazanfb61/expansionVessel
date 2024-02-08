<script setup>
import { ref } from "vue";


const navBar = ref(null);
</script>

<template>
  <div>
    <v-app-bar class="" style="background-image: linear-gradient(transparent)" flat="true" scroll-behavior="elevate" scroll-threshold="400">
      <v-app-bar-title
        class="text-white ml-10"
        style="letter-spacing: 8px; font-size: 2rem; font-weight: 600"
      >
        ARMA
      </v-app-bar-title>
      <v-spacer></v-spacer>
      <v-btn class="text-white" icon="mdi-view-headline "  @click="navBar = !navBar"></v-btn>
    </v-app-bar>
    <v-navigation-drawer location="right" v-model="navBar" temporary>
      <v-list-item link title="List Item 1"></v-list-item>
      <v-list-item link title="List Item 2"></v-list-item>
      <v-list-item link title="List Item 3"></v-list-item>
    </v-navigation-drawer>
  </div>
</template>

<style>
nav > * {
  text-decoration: none;
}
</style>
