<template>
  <div class="color">
    <div class=" mx-auto max-w-5xl" id="container">
      <div class="  flex flex-col   w-full      m-auto  p-3">
        <app-header></app-header>
        <app-projects></app-projects>
        <footer
          class="   p-5   rounded-2xl  shadow-md   flex-row flex justify-center items-center mt-7"
        >
          <a class="text-lg font-light" :href="link"
            ><span>{{ made }}</span>
            <font-awesome-icon class="text-red-800 " :icon="['fas', 'heart']" />
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
footer {
  background-color: #f8f9fa;
}
.color {
  background-color: #e1e5f2;
}
</style>
