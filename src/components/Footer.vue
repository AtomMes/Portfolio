<template>
  <div class="bg-[#1c2742]" id="contact">
    <div
      class="w-full h-full max-w-[1000px] mx-auto flex flex-col lg:flex-row items-center py-8 gap-5"
    >
      <p
        class="text-white text-[30px] border-b lg:border-b-0 lg:border-r lg:pr-10 lg:pb-0 pb-5 lg:mr-5 whitespace-nowrap"
      >
        Get In Touch
      </p>
      <div class="flex gap-5 flex-col-reverse items-center md:flex-row">
        <a
          :href="'mailto:' + mail[1]"
          class="flex items-center flex-col sm:flex-row text-[#fff] duration-100 hover:text-[#33b8c2] bg-[#182239] w-fit px-4 cursor-pointer py-2 rounded-lg"
        >
          <img :src="mail[0]" class="h-[45px] w-auto" />
          <p class="text-[20px] pl-2">{{ mail[1] }}</p>
        </a>
        <a
          :href="'tel:' + call[1]"
          class="flex items-center flex-col sm:flex-row text-[#fff] duration-100 hover:text-[#33b8c2] bg-[#182239] w-fit px-4 cursor-pointer py-2 rounded-lg"
        >
          <img :src="call[0]" class="h-[45px] w-auto" />
          <p class="text-[20px] pl-2">{{ call[1] }}</p>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import mail from "../assets/mail.png";
import call from "../assets/call.png";

export default {
  name: "Footer",
  data() {
    return {
      mail: [mail, "mesropyann.artem@gmail.com"],
      call: [call, "+374-98-39-39-78"],
    };
  },
};
</script>
