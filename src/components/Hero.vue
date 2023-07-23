<template>
  <div class="bg-[#182239] w-full max-w-[1000px] mx-auto pb-20" id="home">
    <div
      class="flex flex-col-reverse lg:flex-row items-center gap-[50px] pt-[15%]"
    >
      <div
        class="text-white w-[70%] flex flex-col gap-[30px] text-center lg:text-left"
      >
        <p class="text-[50px] font-bold">Front-End Developer</p>
        <p class="text-[18px]">
          Hello, I'm Artem Mesropyan, a 17-year-old self-taught front-end
          developer from Armenia.
        </p>
        <div class="flex self-center lg:self-start">
          <div
            v-for="(imageSrc, i) in socialMediaImages"
            :key="i"
            @click="navigateToLink(imageSrc.to)"
            class="ease-in-out duration-300 hover:scale-105 hover:-translate-y-1"
          >
            <img :src="imageSrc.url" :alt="imageSrc.url" class="h-[55px]" />
          </div>
        </div>
      </div>
      <div class=" w-[80%] sm:w-[40%]">
        <img src="../assets/PFP.jpg" alt="PFP" class="rounded-[60px]" />
      </div>
    </div>
    <div
      class="flex justify-center lg:justify-start gap-6 items-center text-white text-[25px] pt-[70px]"
    >
      <p>Main Stack:</p>
      <div class="flex flex-wrap items-center justify-center gap-6">
        <div
          v-for="(imageSrc, i) in techStack"
          :key="i"
          class="ease-in-out duration-300 hover:scale-105 hover:-translate-y-1 relative"
        >
          <img :src="imageSrc[0]" :alt="imageSrc[1]" class="h-[40px]" />
          <div
            class="flex text-[16px] w-full whitespace-nowrap justify-center items-end absolute top-0 h-[160%] duration-300 text-opacity-0 hover:text-opacity-100 text-white"
          >
            {{ imageSrc[1] }}
          </div>
        </div>
      </div>
    </div>
    <div></div>
  </div>
</template>

<script>
import telegram from "../assets/telegram.png";
import whatsapp from "../assets/whatsapp.png";
import linkedin from "../assets/linkedin.png";
import github from "../assets/github.png";
import react from "../assets/react.png";
import typescript from "../assets/typescript.png";
import next from "../assets/next.png";
import javascript from "../assets/javascript.png";
import cv from "../assets/cv3.png";

import githubWhite from "../assets/github-white.png";
import vue from "../assets/vue.png";

export default {
  name: "Hero",
  data() {
    return {
      socialMediaImages: [
        { url: cv, to: "https://bit.ly/Artem_Mesropyan_CV" },
        { url: linkedin, to: "https://linkedin.com/in/artem-mesropyan/" },
        { url: whatsapp, to: "https://wa.me/qr/F6KLHQ753GPCE1" },
        { url: telegram, to: "https://t.me/attom1" },
        { url: github, to: "https://github.com/AtomMes" },
      ],
      techStack: [
        [react, "React/React Native"],
        [next, "Next.js"],
        [vue, "Vue, Vuex"],
        [javascript, "JavaScript"],
        [typescript, "TypeScript"],
      ],
    };
  },
  methods: {
    navigateToLink(link) {
      window.open(link, "_blank");
    },
  },
};
</script>
<!-- 
import telegram from "../assets/telegram.png";
import whatsapp from "../assets/whatsapp.png";
import linkedin from "../assets/linkedin.png";
import github from "../assets/github.png";
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
import tailwind from "../assets/tailwind.png"; -->
<!-- 
{ url: html, to: "https://www.w3schools.com/html/" },
{ url: css, to: "https://www.w3schools.com/css/" },
{ url: typescript, to: "https://www.typescriptlang.org/" },
{ url: javascript, to: "https://javascript.info/" },
{ url: react, to: "https://reactjs.org/" },
{ url: next, to: "https://nextjs.org/" },
{ url: vue, to: "https://vuejs.org/" },
{ url: redux, to: "https://redux.js.org/" },
{ url: mui, to: "https://mui.com/" },
{ url: firebase, to: "https://firebase.google.com/" },
{ url: sass, to: "https://sass-lang.com/" },
{ url: git, to: "https://git-scm.com/" },
{ url: githubWhite, to: "https://github.com/AtomMes" },
{ url: tailwind, to: "https://tailwindcss.com/" }, -->

<!-- <p class="text-[18px]">
  Hello, I'm Artem Mesropyan, a 17-year-old self-taught front-end
  developer from Armenia. With over a year of experience in web
  development, I enjoy working with React Native, Next.js, and Vue to
  create cool and user-friendly websites. I am constantly learning to keep
  up with the latest web dev tech. Apart from coding, I also have a
  passion for chess, playing football with friends, and listening to
  music. Making friends from all walks of life is my jam.
</p> -->
