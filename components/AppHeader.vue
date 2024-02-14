<script setup>
import { ref } from "vue";

const navBar = ref(null);
const open = ref(["Kurumsal"]);
const menulinks = ref([
  ["/misyonumuz", "Misyonumuz"],
  ["/kalite", "Kalite"],
  ["/tanitim", "Tanıtım"],
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
      <v-app-bar-title>
        <nuxt-link
          class="nav-link text-white ml-sm-10"
          style="
            letter-spacing: 8px;
            font-size: 2rem;
            font-weight: 600;
            text-decoration: none;
          "
          to="/"
        >
          ARMA
        </nuxt-link>
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
        <nuxt-link to="/" class="nav-link">
          <v-list-item title="Anasayfa"></v-list-item>
        </nuxt-link>
        <v-list-group value="Kurumsal">
          <template v-slot:activator="{ props }">
            <v-list-item v-bind="props">
              <nuxt-link
                
                class="mb-1 nav-link"
                to="/kurumsal"
                >Kurumsal</nuxt-link
              >
            </v-list-item>
          </template>

          <nuxt-link
            v-for="([path, name], i) in menulinks"
            class="nav-link"
            :to="path"
          >
            <v-list-item :key="i" :title="name" :value="i"> </v-list-item>
          </nuxt-link>
        </v-list-group>
        <nuxt-link to="/urunlerimiz" class="nav-link">
          <v-list-item title="Ürünlerimiz"></v-list-item>
        </nuxt-link>
        <nuxt-link to="/iletisim" class="nav-link">
          <v-list-item title="İletişim"></v-list-item>
        </nuxt-link>
      </v-list>

    </v-navigation-drawer>
  </div>
</template>

<style>
.nav-link {
  text-decoration: underline;
  text-underline-offset: 2px;
  color: black;
  text-decoration-thickness:1px;
}
</style>
