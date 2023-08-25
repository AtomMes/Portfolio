<template>
  <div class="w-full max-w-[1000px] mx-auto py-[80px]" id="projects">
    <p class="text-white text-[30px] pb-10 pl-2 text-center lg:text-left">
      Some Of My Projects
    </p>
    <div v-for="project in projects" :key="project.index" class="px-3">
      <Project :project="project" :index="project.index" />
    </div>
    <div v-for="project in mobile" :key="project.index" class="px-3">
      <MobileProject :project="project" :index="project.index" />
    </div>
  </div>
</template>

<script>
import react from "../assets/react.png";
import angular from "../assets/angular.png";
import tailwind from "../assets/tailwind.png";
import mui from "../assets/mui.svg";
import firebase from "../assets/firebase.png";
import typescript from "../assets/typescript.png";
import javascript from "../assets/javascript.png";
import memberHome from "../assets/projects/member.png";
import redux from "../assets/redux.png";
import fastFood from "../assets/projects/fast.png";
import memberbase from "../assets/projects/memberbase.png";
import mobileHome from "../assets/projects/mobileHome.jpg";
import mobileCart from "../assets/projects/mobileCart.jpg";
import mobileInfo from "../assets/projects/mobileInfo.jpg";
import mobileFull from "../assets/projects/mobileFull.jpg";
import Project from "./Project.vue";
import MobileProject from "./MobileProject.vue";

export default {
  name: "Projects",
  data() {
    return {
      socialMediaImages: [
        { url: react, to: "https://linkedin.com/in/artem-mesropyan/" },
        { url: mui, to: "https://wa.me/qr/F6KLHQ753GPCE1" },
        { url: firebase, to: "https://t.me/attom1" },
        { url: typescript, to: "https://github.com/AtomMes" },
      ],
      projects: [
        {
          title: "Member",
          description:
            "Member is a fully functional social media platform that allows users to connect, chat, share posts and so on.",
          link: "https://member-at.netlify.app",
          github: "https://github.com/AtomMes/Member",
          image: memberHome,
          icons: [
            [react, "React"],
            [mui, "MUI"],
            [firebase, "Firebase"],
            [typescript, "TypeScript"],
            [redux, "Redux Toolkit"],
          ],
          index: 1,
        },
        {
          title: "Memberbase",
          description:
            "Memberbase is a free modern website with membership functionality. It makes it easy to build a website with gated content.",
          link: "https://memberbase-at.netlify.app",
          github: "https://github.com/AtomMes/Memberbase",
          image: memberbase,
          icons: [
            [angular, "Angular"],
            [typescript, "TypeScript"],
            [tailwind, "Tailwind"],
          ],
          index: 2,
        },
        {
          title: "Fast Food",
          description:
            "Fast Food is an online ordering platform where you can order your favorite snack just by few clicks.",
          link: "https://fast-food-at.netlify.app",
          github: "https://github.com/AtomMes/Fast-Food",
          image: fastFood,
          icons: [
            [react, "React"],
            [redux, "Redux Toolkit"],
            [javascript, "JavaScript"],
            [mui, "MUI"],
          ],
          index: 3,
        },
      ],
      mobile: [
        {
          title: "Fast Food Mobile",
          description:
            " The Fast Food and Fast Food Mobile are part of the same project, that allows users to order some snacks.",
          link: "https://expo.dev/@atommes/fast-food-mobile",
          github: "https://github.com/AtomMes/Fast-Food-Mobile",
          image: [mobileHome, mobileCart, mobileFull, mobileInfo],
          icons: [
            [react, "React Native"],
            [typescript, "TypeScript"],
            [mui, "MUI"],
            [redux, "Redux Toolkit"],
          ],
          index: 4,
        },
      ],
    };
  },
  methods: {
    navigateToLink(url) {
      window.open(url, "_blank");
    },
  },
  components: {
    Project,
    MobileProject,
  },
};
</script>
