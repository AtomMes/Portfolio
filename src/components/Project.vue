<template lang="">
  <div
    :class="{ 'lg:flex-row-reverse': index % 2 !== 1 }"
    class="flex flex-col lg:flex-row gap-[50px] py-5 px-5 lg:py-10 lg:px-10 bg-[#1c2742] rounded-2xl mb-[80px] items-center justify-center"
  >
    <div
      ref="imageContainer"
      class="w-fit h-[350px] rounded-lg no-scrollbar overflow-auto lg:w-[65%]"
      @mouseover="startScrolling"
      @mouseleave="stopScrolling"
    >
      <img :src="project.image" :alt="project.title" class="w-full" />
    </div>
    <div
      class="w-[100%] lg:w-[35%] text-white flex flex-col gap-3 items-center"
    >
      <p class="font-bold text-[25px]">{{ project.title }}</p>
      <p class="text-center text-[#dcdbdb] text-[20px]">
        {{ project.description }}
      </p>
      <div class="flex gap-3 my-4">
        <div
          v-for="(icon, i) in project.icons"
          :key="i"
          class="flex justify-center items-center ease-in-out duration-300 hover:scale-105 hover:-translate-y-1 relative"
        >
          <img :src="icon[0]" :alt="icon[1]" class="h-[40px]" />
          <div
            class="flex whitespace-nowrap justify-center items-end absolute top-0 h-[160%] duration-300 text-opacity-0 hover:text-opacity-100 text-white"
          >
            {{ icon[1] }}
          </div>
        </div>
      </div>
      <div class="flex gap-5">
        <button
          class="border border-solid border-white px-4 pb-[1px] h-[35px] font-semibold rounded-md ease-in-out duration-300 hover:bg-white hover:text-[#1c2742]"
          @click="navigateToLink(project.github)"
        >
          Code
        </button>
        <button
          class="border border-solid border-white px-4 pb-[1px] h-[35px] font-semibold rounded-md ease-in-out duration-300 hover:bg-white hover:text-[#1c2742]"
          @click="navigateToLink(project.link)"
        >
          Review
        </button>
      </div>
    </div>
  </div>
</template>

<style>
.no-scrollbar {
  scrollbar-width: none;
  -ms-overflow-style: none;
  &::-webkit-scrollbar {
    width: 0;
    height: 0;
  }

  &::-webkit-scrollbar-thumb {
    background-color: transparent;
  }
}
</style>

<script>
export default {
  name: "Project",
  props: {
    project: {
      type: Object,
      required: true,
    },
    index: {
      type: Number,
      required: true,
    },
  },
  data() {
    return {
      intervalId: null,
    };
  },
  methods: {
    navigateToLink(link) {
      window.open(link, "_blank");
    },
    created() {
      this.property = "Example property update.";

      console.log(
        "propertyComputed will update, as this.property is now reactive."
      );
    },
    startScrolling() {
      console.log("index is", this.index);
      this.intervalId = setInterval(() => {
        const container = this.$refs.imageContainer;
        if (container) {
          container.scrollTop += 1;
          if (
            container.scrollTop >=
            container.scrollHeight - container.clientHeight
          ) {
            clearInterval(this.intervalId);
          }
        }
      }, 1);
    },
    stopScrolling() {
      clearInterval(this.intervalId);
      const container = this.$refs.imageContainer;
      if (container) {
        container.scrollTo({
          top: 0,
          behavior: "smooth",
        });
      }
    },
  },
};
</script>
