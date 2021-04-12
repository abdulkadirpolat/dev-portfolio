<template>
  <figure>
    <img
      class=" transition-transform  duration-300 transform hover:scale-105 shadow-md w-52 h-52 md:w-48 md:h-auto md:rounded-none rounded-full md:mx-auto  mr-8"
      src="/portfolio.png"
      alt=""
      width="384"
      height="512"
    />
    <div class=" md:text-center  md:pt-0 font-light ">
      <p class="text-lg   ">Hi, my name is</p>
      <p class="text-4xl font-semibold " v-for="full in allData" :key="full">
        {{ full.fullname }}
      </p>
      <p
        class="text-lg  my-7  md:m-3  md:mx-0 md:mb-8 "
        v-for="regarding in allData"
        :key="regarding"
      >
        {{ regarding.about }}
      </p>

      <nuxt-link class="links" to="/resume" target="_blank">RESUME</nuxt-link>
      <a class="links" :href="link">CONTACT</a>
    </div>
  </figure>
</template>
<script>
export default {
  data() {
    return {
      allData: [],
      link:'https://www.linkedin.com/in/abdulkadir-polat-1b282b1b7'
    };
  },
  async fetch() {
    this.allData = await fetch("/data.json").then(res => res.json());
  }
};
</script>
<style lang="postcss" scoped>
figure {
  background-color: #f8f9fa;
  @apply md:block p-8   rounded-2xl  shadow-md   flex-row flex items-center mt-7;
}
.links {
  background-color: #e1e5f2;
  @apply 2sm:text-xs rounded-3xl font-light  py-2 px-5 text-center hover:bg-purple-800 hover:text-white;
}
</style>
