<template>
  <div id="container">
    <div class="mx-auto max-w-5xl ">
      <div class="flex flex-col w-full m-auto p-3">
        <app-header></app-header>
        <profile></profile>
        <frontent></frontent>
        <dev-tools></dev-tools>

        <footer
          class="select-none p-5 rounded-2xl shadow-md flex-row flex justify-center items-center mt-7"
        >
          <a class="text-lg font-light" :href="link" target="_blank"
            ><span>{{ made }}</span>
            <font-awesome-icon class="text-red-800" :icon="['fas','heart']" />
            <span>{{ made }} </span></a
          >
        </footer>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      made: "made with",
      link: "https://github.com/abdulkadirpolat/abdulkadirpolat.net"
    };
  }
};
</script>

<style lang="postcss" scoped>
#container {
  background-color: #e1e5f2;
}
footer {
  background-color: #f8f9fa;
}
</style>
