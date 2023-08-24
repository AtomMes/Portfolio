<template>
  <div class="h-full flex items-center justify-center">
    <img :src="icon[0]" :alt="icon[1]" :class="`h-[${size}]`" />
    <div
      class="flex whitespace-nowrap justify-center items-end absolute top-0 pt-[65px] h-full duration-300 text-opacity-0 hover:text-opacity-100 text-white"
      :class="{ 'pt-[110px]': about }"
    >
      {{ icon[1] }}
    </div>
  </div>
</template>

<script>
export default {
  name: "Skill",
  props: {
    icon: {
      type: Array,
      required: true,
    },
    size: {
      type: String,
      required: true,
    },
    about: {
      type: Boolean,
      required: false,
    },
  },
};
</script>
