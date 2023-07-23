<template>
  <div>
    <Hero />
    <About />
    <Projects />
    <Footer />
  </div>
</template>

<script>
import Hero from "@/components/Hero.vue";
import Projects from "@/components/Projects.vue";
import About from "@/components/About.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "HomeView",
  components: { Hero, Projects, About, Footer },
};
</script>
