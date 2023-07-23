<template lang="">
  <div class="sticky top-0 left-0 z-50 px-16 bg-[#1c2742]">
    <nav v-if="$data.$screen.xs">
      <div
        class="w-full max-w-[1000px] mx-auto text-white flex justify-end items-center gap-6 py-5"
      >
        <a
          v-for="(button, index) in buttons"
          :key="index"
          :href="'#' + button.toLowerCase()"
        >
          <button>{{ button }}</button>
        </a>
      </div>
    </nav>
    <nav v-else>
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
            class="absolute right-0 mt-2 bg-white rounded-lg shadow-lg"
          >
            <a
              v-for="(button, index) in buttons"
              :key="index"
              :href="'#' + button.toLowerCase()"
            >
              <button class="block px-4 py-2 text-[#1c2742]">
                {{ button }}
              </button>
            </a>
          </div>
        </div>
      </div>
    </nav>
  </div>
</template>
<script>
export default {
  name: "Navbar",
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
      buttons: ["Home", "About", "Projects", "Contact"],
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
<style lang=""></style>
