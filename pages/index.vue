<template>
  <div v-if="loading" class=" mx-auto max-w-4xl" id="container">
    <div class="  flex flex-col   w-full      m-auto  p-3">
      <app-header></app-header>
      <profile></profile>
      <frontent></frontent>
      <dev-tools></dev-tools>

      <footer
        class="select-none   p-5   rounded-2xl  shadow-md   flex-row flex justify-center items-center mt-7"
      >
        <a class="text-lg font-light" :href="link" target="_blank"
          ><span>{{ made }}</span>
          <font-awesome-icon class="text-red-800 " :icon="['fas', 'heart']" />
          <span>{{ made }} </span></a
        >
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      made: "made with",
      link: "https://github.com/abdulkadirpolat/abdulkadirpolat.net",
      loading: false
    };
  },
  methods: {
    start() {
      this.loading = true;
    },
    finish() {
      this.loading = false;
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.$nuxt.$loading.start();
      setTimeout(() => this.$nuxt.$loading.this.finish(), 500);
    });
  },

  loadingIndicator: {
    name: "circle",
    color: "#3B8070",
    background: "green"
  }
};
</script>

<style lang="postcss" scoped>
html {
  background-color: #e1e5f2;
}
footer {
  background-color: #f8f9fa;
}
</style>
