<template>
  <div class="project">
    <div
      class="h-80 sm:h-112 rounded-2xl shadow-md element"
      v-for="all in allData.projects"
      :key="all"
    >
      <div
        class="flex flex-col justify-between h-full rounded-2xl overflow-hidden text-center"
      >
        <div class="w-full h-44 md:h-64 sm:h-64 overflow-hidden rounded-2xl">
          <img
            loading="lazy"
            :src="all.image"
            class="max-w-full min-h-full h-auto align-middle object-cover rounded-2xl"
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
        <div class="h-10 m-4 flex">
          <a :href="all.source" class="btn" target="_blank">Source</a>
          <a :href="all.live" class="btn " target="_blank">Preview</a>
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
  background-color: #e1e5f2;
  @apply select-none font-light relative rounded-2xl mt-7 grid grid-cols-3 gap-4 2md:grid-cols-2 sm:grid-cols-1;
}
.btn {
  background: #e1e5f2;
  @apply rounded-3xl px-5 py-2 mr-2 w-full hover:bg-purple-800 hover:text-white;
}
.element {
  background-color: #f8f9fa;
}
</style>
