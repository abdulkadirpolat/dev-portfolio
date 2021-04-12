<template>
  <div class="project">
    <div class="h-60 md:h-96" v-for="all in allData.projects" :key="all">
      <div
        class="flex flex-col justify-between  h-full bg-gray-200 rounded-2xl overflow-hidden text-center"
      >
        <div class="w-full h-44 md:h-64 overflow-hidden">
          <img loading="lazy" :src="all.image" class="img" />
        </div>
        <p>{{ all.name }}</p>
        <div>
          <span
            class="inline text-white rounded-2xl bg-gray-800  mr-2 px-4 "
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
  @apply select-none font-light relative  rounded-2xl shadow-md mt-7 p-2   grid   grid-cols-3 gap-4 md:grid-cols-2  sm:grid-cols-1;
}
.btn {
  @apply bg-gray-400 rounded-2xl px-5 py-2 mr-2;
}
.img{
  background: center;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover ;
}
</style>
