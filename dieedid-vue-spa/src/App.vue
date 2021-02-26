<template>
  <div id="app">
    <div class="wrapper">
      <Header class="test" />

      <main class="main">
        <div class="container">
          <Process />
        </div>
      </main>

      <Footer class="test2" />
    </div>
  </div>
</template>

<script>
import Header from "@/components/header/Header.vue";
import Footer from "@/components/footer/Footer.vue";
import Process from "@/components/process/Process.vue";

export default {
  components: {
    Header,
    Footer,
    Process
  }
};
</script>

<style lang="scss">
.wrapper {
  background: url("./assets/images/first-bg.jpg");
  @include bg-img-settings;
}
.wrapper {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: auto 1fr auto;
  gap: 0px 0px;
}
.maine {
  display: block;
}
</style>
