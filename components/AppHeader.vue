<script setup>
import { ref } from "vue";

const navBar = ref(null);
const open = ref(["Kurumsal"]);
const links = ref([
  ["/", "Misyonumuz"],
  ["/kurumsal", "Kalite"],
  ["/urunlerimiz", "Ekibimiz"],
  ["/iletisim", "Tanıtım"],
]);
</script>

<template>
  <div>
    <v-app-bar
      class="rounded-b-lg"
      style="background: rgb(255, 0, 0); backdrop-filter: blur(1.5rem)"
      elevation="0"
      scroll-behavior="elevate"
      scroll-threshold="400"
    >
      <v-app-bar-title
        class="text-white ml-10"
        style="letter-spacing: 8px; font-size: 2rem; font-weight: 600"
      >
        ARMA
      </v-app-bar-title>
      <v-spacer></v-spacer>
      <v-btn
        class="text-white d-sm-none"
        icon="mdi-view-headline "
        @click="navBar = !navBar"
      ></v-btn>
    </v-app-bar>
    <v-navigation-drawer location="top" v-model="navBar" temporary>
      <v-list v-model="open">
        <v-list-group value="Kurumsal">
          <template v-slot:activator="{ props }">
            <v-list-item v-bind="props">
              <nuxt-link to="/kurumsal">Kurumsal</nuxt-link>
            </v-list-item>
          </template>

          <nuxt-link
            v-for="([path, name], i) in links"
            style="text-decoration: none"
            :to="path"
          >
            <v-list-item :key="i" :title="name" :value="i"> </v-list-item>
          </nuxt-link>
        </v-list-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<style></style>
