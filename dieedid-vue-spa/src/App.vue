<template>
  <div id="app">
    <div class="wrapper">
      <Header />
      <Footer />
    </div>
  </div>
</template>

<script>
import Header from "@/components/header/Header.vue";
import Footer from "@/components/footer/Footer.vue";

export default {
  components: {
    Header,
    Footer,
  },
};
</script>

<style lang="scss">
.wrapper {
  background: url("./assets/images/first-bg.jpg");
  @include bg-img-settings;
}
</style>
