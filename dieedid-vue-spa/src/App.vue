<template>
  <div id="app">
    <div class="wrapper">
      <div class="content">
        <Header />
        <Gender />
        <PhysicalActivity />
        <Process />
      </div>

      <Footer />
    </div>
  </div>
</template>

<script>
import Header from "@/components/header/Header.vue";
import Footer from "@/components/footer/Footer.vue";
import Process from "@/components/process/Process.vue";
import Gender from "@/components/screens/Gender.vue";
import PhysicalActivity from "@/components/screens/PhysicalActivity.vue";

export default {
  components: {
    Header,
    Footer,
    Process,
    Gender,
    PhysicalActivity
  }
};
</script>

<style lang="scss">
#app {
  height: 100%;
}
.wrapper {
  background: url("./assets/images/first-bg.jpg");
  @include bg-img-settings;
  min-height: 100%;
  display: flex;
  flex-flow: column;
}
.content {
  min-height: 100%;
  flex: 1 0 auto;
}

.wrapper__inner {
  min-height: 100%;
  display: flex;
  flex-flow: column;
}
.content__inner {
  height: 100%;
  flex: 1 0 auto;
}
</style>
