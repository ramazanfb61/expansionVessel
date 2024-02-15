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
      class="rounded-b-lg border "
      style="background: rgb(255, 0, 0); "
      elevation="0"
      
  
      scroll-behavior="shrink"
      scroll-threshold="400"
    >
      <v-app-bar-title class="border  w-100">
        <nuxt-link
          class="nav-link text-white w-50 ml-md-5 ml-md-10"
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
      <v-row class="d-none d-sm-flex" style="width: 250px;font-weight: 600;font-size: 18px;">
        <v-col class="border">
          <nuxt-link style="text-decoration: none;" class="text-white" to="/">Anasayfa</nuxt-link>
        </v-col>
        <v-col class="border">
          <nuxt-link style="text-decoration: none;" class="text-white" to="/kurumsal">Kurumsal</nuxt-link>
        </v-col>
        <v-col class="border">
          <nuxt-link style="text-decoration: none;" class="text-white" to="/urunlerimiz">Ürünlerimiz</nuxt-link>
        </v-col>
        <v-col class="border">
          <nuxt-link style="text-decoration: none;" class="text-white" to="/iletisim">İletişim</nuxt-link>
        </v-col>
      </v-row>
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
.nav-link-wide{
  transition: 0.5s ease-in text-decoration;
}
.underline-transition:hover{
  text-decoration: underline;
}

</style>
