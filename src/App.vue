<template>
  <div id="app">
    <router-view name="header"></router-view>
    <main>
      <!-- <fade-transition origin="center" mode="out-in" :duration="250"> -->
        <router-view />
      <!-- </fade-transition> -->
      <Basenav></Basenav>
    </main>
    <router-view name="footer"></router-view>
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <Deals></Deals>
  </div>
</template>

<script>
// import { FadeTransition } from "vue2-transitions";
import HelloWorld from "./components/HelloWorld.vue";
import Deals from "./components/Deals.vue";

export default {
  components: {
    // FadeTransition,
    HelloWorld,
    Deals,
  },
};
</script>
