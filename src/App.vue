<template>
  <div id="app" class="bg-[#182239]">
    <nav
      v-if="$data.$screen.md"
      class="bg-[#1c2742] sticky top-0 left-0 z-50 px-16"
    >
      <div
        class="w-full max-w-[1000px] mx-auto text-white flex justify-end items-center gap-6 py-5"
      >
        <a href="#home"><button>Home</button></a>
        <a href="#about"><button>About</button></a>
        <a href="#projects"><button>Projects</button></a>
        <a href="#contact"><button>Contact</button></a>
      </div>
    </nav>
    <nav v-else class="bg-[#1c2742] sticky top-0 left-0 z-50 px-16">
      <div
        class="w-full max-w-[1000px] mx-auto text-white flex justify-end items-center gap-6 py-5"
      >
        <div class="relative" @click="toggleDropdown">
          <button class="cursor-pointer">
            <div
              class="border-y h-[13px] w-[26px] flex items-center justify-center"
            >
              <div class="border-b border-white w-[26px] mb-[1px]" />
            </div>
          </button>
          <div
            v-if="showDropdown"
            @click.away="closeDropdown"
            class="absolute right-0 mt-2 bg-white rounded-lg shadow-lg"
          >
            <!-- Use anchors with "href" attribute to scroll to each section -->
            <a href="#home"
              ><button class="block px-4 py-2 text-[#1c2742]">Home</button></a
            >
            <a href="#about"
              ><button class="block px-4 py-2 text-[#1c2742]">About</button></a
            >
            <a href="#projects"
              ><button class="block px-4 py-2 text-[#1c2742]">
                Projects
              </button></a
            >
            <a href="#contact"
              ><button class="block px-4 py-2 text-[#1c2742]">
                Contact
              </button></a
            >
          </div>
        </div>
      </div>
    </nav>

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
import HomeView from "./views/HomeView.vue";

export default {
  name: "App",
  components: {
    HomeView,
  },
  data() {
    return {
      $screen: {
        xs: false,
        sm: false,
        md: false,
        lg: false,
        xl: false,
      },
      showDropdown: false, 
    };
  },
  mounted() {
    this.handleResize();
    window.addEventListener("resize", this.handleResize);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.handleResize);
  },
  methods: {
    handleResize() {
      const breakpoints = {
        xs: 640,
        sm: 768,
        md: 1024,
        lg: 1280,
        xl: 1536,
      };
      for (const breakpoint in breakpoints) {
        this.$set(
          this.$data.$screen,
          breakpoint,
          window.innerWidth >= breakpoints[breakpoint]
        );
      }
    },
    toggleDropdown() {
      this.showDropdown = !this.showDropdown;
    },
    closeDropdown() {
      this.showDropdown = false;
    },
  },
};
</script>
