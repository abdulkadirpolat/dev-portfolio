<template>
  <div class="project">
    <div class="h-60 md:h-96 " v-for="all in allData.projects" :key="all">
      <div
        class="flex flex-col justify-between  h-full  rounded-2xl overflow-hidden text-center"
      >
        <div
          class="w-full h-52 md:h-64 sm:h-64   overflow-hidden     rounded-2xl"
        >
          <img
            loading="lazy"
            :src="all.image"
            class="p-2 rounded-3xl max-w-full min-h-full  h-auto align-middle"
          />
        </div>
        <p class="font-normal">{{ all.name }}</p>
        <div>
          <span
            class="inline text-white rounded-2xl bg-gray-700  mr-2 px-4 "
            v-for="together in all.tech"
            :key="together"
          >
            {{ together }}
          </span>
        </div>
        <div class="h-12 mt-4">
          <a :href="all.source" class="btn">Source</a>
          <a :href="all.live" class="btn ">Preview</a>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      allData: []
    };
  },
  async fetch() {
    this.allData = await fetch("/data.json").then(res => res.json());
  }
};
</script>
<style lang="postcss" scoped>
.project {
  background-color: #f8f9fa;
  @apply select-none font-light relative  rounded-2xl shadow-md mt-7 p-2   grid   grid-cols-3 gap-4 md:grid-cols-2  sm:grid-cols-1 ;
}
.btn {
  background: #e1e5f2;
  @apply rounded-2xl px-5 py-2 mr-2 hover:bg-purple-800 hover:text-white;
}
/* .img{
  background: center;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover ;
} */
</style>
