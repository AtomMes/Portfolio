<template>
  <div id="app" class="bg-[#182239]">
    <HomeView />
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}
</style>

<script>
import HomeView from "./views/HomeView.vue";

export default {
  name: "App",
  components: {
    HomeView,
  },
};
</script>
