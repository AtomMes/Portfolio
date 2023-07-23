<template>
  <div>
    <Navbar />
    <Hero />
    <About />
    <Projects />
    <Contact />
  </div>
</template>

<style>
button {
  background-color: transparent;
  border: none;
  color: white;
  cursor: pointer;
  font-size: 16px;
}

button:hover {
  opacity: 0.8;
}
</style>

<script>
import Hero from "@/components/Hero.vue";
import Projects from "@/components/Projects.vue";
import About from "@/components/About.vue";
import Contact from "@/components/Contact.vue";
import Navbar from "@/components/Navbar.vue";

export default {
  name: "HomeView",
  components: { Hero, Projects, About, Contact, Navbar },
};
</script>
