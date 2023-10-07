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
          Hello, I'm Artem, a 18-year-old self-taught front-end
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
      <div class="w-[80%] sm:w-[40%]">
        <img src="../assets/PFP.jpg" alt="PFP" class="rounded-[60px]" />
      </div>
    </div>
    <div
      class="px-3 sm:px-0 flex flex-col sm:flex-row justify-center lg:justify-start gap-6 items-center text-white text-[25px] pt-[70px]"
    >
      <p class="whitespace-nowrap">Main Stack</p>
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
import cv from "../assets/cv.png";
import github from "../assets/github.png";
import javascript from "../assets/javascript.png";
import linkedin from "../assets/linkedin.png";
import next from "../assets/next.png";
import react from "../assets/react.png";
import telegram from "../assets/telegram.png";
import typescript from "../assets/typescript.png";
import vue from "../assets/vue.png";
import whatsapp from "../assets/whatsapp.png";
import angular from "../assets/angular.png";

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
        [javascript, "JavaScript"],
        [typescript, "TypeScript"],
        [react, "React/React Native"],
        [vue, "Vue, Vuex"],
        [next, "Next.js"],
        [angular, "Angular"],
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
