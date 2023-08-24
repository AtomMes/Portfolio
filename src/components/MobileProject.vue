<template lang="">
  <div
    :class="{ 'lg:flex-row-reverse': index % 2 === 0 }"
    class="flex mr-0 lg:mr-1 flex-col items-center lg:flex-row here py-5 px-5 lg:py-10 lg:px-10 md:gap-[40px] bg-[#1c2742] rounded-2xl mb-[80px]"
  >
    <div class="flex flex-wrap w-[100%] lg:w-[65%]">
      <div
        v-for="(img, i) in project.image"
        class="w-[49%] md:w-[24%] h-[320px] mr-[1px] here mb-5 md:mb-0 flex items-center justify-center"
      >
        <img
          :src="img"
          :alt="img"
          class="h-fit max-h-[320px] rounded-md object-contain"
          :class="
            isMobile
              ? null
              : 'sm:hover:absolute  sm:hover:z-10 sm:hover:scale-[2] ease-in-out duration-300'
          "
        />
      </div>
    </div>

    <div
      class="w-[100%] lg:w-[35%] pt-10 lg:pt-0 text-white flex flex-col gap-3 items-center"
    >
      <p class="font-bold text-[25px]">{{ project.title }}</p>
      <p class="text-center text-[#dcdbdb]">
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
          class="border border-solid border-white  px-4 pb-[1px] h-[35px] font-semibold rounded-md ease-in-out duration-300 hover:bg-white hover:text-[#1c2742]"
          @click="navigateToLink(project.github)"
        >
          Code
        </button>
        <button
          class="border border-solid border-white  px-4 pb-[1px] h-[35px] font-semibold rounded-md ease-in-out duration-300 hover:bg-white hover:text-[#1c2742]"
          @click="navigateToLink(project.link)"
        >
          Review
        </button>
      </div>
    </div>
  </div>
</template>

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
  methods: {
    navigateToLink(link) {
      window.open(link, "_blank");
    },
    checkIfMobile() {
      const isMobile =
        /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(
          navigator.userAgent
        );
      return isMobile;
    },
  },
};
</script>
