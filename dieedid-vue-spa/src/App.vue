<template>
  <div id="app">
    <div class="wrapper">
      <div class="content">
        <Header />
        <Gender v-if="this.section.gender.active" />
        <PhysicalActivity v-if="this.section.physicalActivity.active" />
        <PhysicalExercise v-if="this.section.physicalExercise.active" />
        <BodyMassIndex v-if="this.section.bodyMassIndex.active" />
        <Process @processSection="addInfo" :section="section" />
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
import PhysicalExercise from "@/components/screens/PhysicalExercise.vue";
import BodyMassIndex from "@/components/screens/BodyMassIndex.vue";

export default {
  components: {
    Header,
    Footer,
    Process,
    Gender,
    PhysicalActivity,
    PhysicalExercise,
    BodyMassIndex
  },
  data() {
    return {
      section: {
        gender: {
          name: "Пол",
          active: false,
          id: 0
        },
        physicalActivity: {
          name: "Физическая активность",
          active: false,
          id: 1
        },
        physicalExercise: {
          name: "Физические нагрузки",
          active: false,
          id: 2
        },
        bodyMassIndex: {
          name: "Индексы массы тела",
          active: true,
          id: 3
        },
        allergy: {
          name: "Аллергия",
          active: false,
          id: 4
        },
        objective: {
          name: "Цели",
          active: false,
          id: 5
        },
        personalData: {
          name: "Личные  данные",
          active: false,
          id: 6
        },
        summary: {
          name: "Сводка",
          active: false,
          id: 7
        }
      }
    };
  },
  methods: {
    addInfo(processSection) {
      this.section = processSection;
    }
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
