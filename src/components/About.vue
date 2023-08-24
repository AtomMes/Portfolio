<template>
  <div class="bg-[#1c2742] py-[90px]" id="about">
    <div
      class="w-full h-full max-w-[1000px] mx-auto flex flex-col-reverse items-center lg:flex-row gap-10 lg:py-10"
    >
      <div class="w-[80%] lg:w-[50%] text-[#fff] flex flex-col items-center">
        <p
          class="text-[30px] font-semibold pb-6 mb-10 border-b mt-6 lg:mt-0 border-[#b0b0c1]"
        >
          Tech Stack
        </p>
        <div class="grid grid-cols-5 gap-5">
          <div
            v-for="(imageSrc, i) in techStack"
            :key="i"
            class="ease-in-out duration-300 hover:scale-105 hover:-translate-y-1 relative"
          >
            <Skill :icon="imageSrc" size="100%" about='true' />
          </div>
        </div>
      </div>
      <div
        class="w-[80%] lg:w-[50%] flex flex-col gap-7 text-center lg:text-left pb-6 border-b border-[#b0b0c1] lg:border-b-0 lg:pb-0"
      >
        <p class="text-[#bff2c8] text-[21px] font-bold">About Me</p>
        <p class="text-white text-[26px] font-semibold">
          A dedicated Front-end Developer based in Vanadzor, Armenia
        </p>
        <p class="text-[19px] text-[#dcdbdb]">
          My name is Artem Mesropyan, I'm a 17-year-old self-taught front-end
          developer from Armenia.
          <br />
          With over a year of experience in web development, I enjoy working
          with Front-end development libraries such as React, Next, Vue, React
          Native, and Angular to create user-friendly websites. I am constantly
          learning to keep up with the latest web dev tech.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import react from "../assets/react.png";
import mui from "../assets/mui.svg";
import firebase from "../assets/firebase.png";
import typescript from "../assets/typescript.png";
import next from "../assets/next.png";
import javascript from "../assets/javascript.png";
import html from "../assets/html.png";
import css from "../assets/css.png";
import sass from "../assets/sass.png";
import git from "../assets/git.png";
import githubWhite from "../assets/github-white.png";
import vue from "../assets/vue.png";
import redux from "../assets/redux.png";
import tailwind from "../assets/tailwind.png";
import angular from "../assets/angular.png";
import Skill from "./Skill.vue";

export default {
  name: "Hero",
  data() {
    return {
      techStack: [
        [html, "HTML"],
        [css, "CSS"],
        [javascript, "JavaScript"],
        [typescript, "TypeScript"],
        [angular, "Angular"],
        [react, "React/React Native"],
        [next, "Next.js"],
        [vue, "Vue, Vuex"],
        [redux, "Redux/Redux Toolkit"],
        [git, "Git"],
        [tailwind, "Tailwind"],
        [sass, "Sass"],
        [githubWhite, "GitHub"],
        [firebase, "Firebase"],
        [mui, "Material-UI"],
      ],
    };
  },
  components: {
    Skill,
  },
};
</script>
