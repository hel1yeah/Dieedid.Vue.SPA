<template>
  <section class="process__wraper">
    <div class="container">
      <div class="process">
        <div class="process__bar"></div>
        <div
          class="process__position"
          v-for="(screen, index) in section"
          :key="index"
        >
          <div
            class="process__dot"
            @click="screenActive(index)"
            :class="{ 'process__dot--active': screen.active }"
          ></div>
          <div class="process__info">
            {{ screen.name }}
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Process",
  data() {
    return {
      section: {
        gender: {
          name: "Пол",
          active: false
        },
        physicalActivity: {
          name: "Физическая активность",
          active: false
        },
        physicalExercise: {
          name: "Физические нагрузки",
          active: false
        },
        bodyMassIndices: {
          name: "Индексы массы тела",
          active: false
        },
        allergy: {
          name: "Аллергия",
          active: false
        },
        personalData: {
          name: "Личные  данные",
          active: false
        },
        summary: {
          name: "Сводка",
          active: false
        }
      }
    };
  },
  methods: {
    screenActive(index) {
      for (const key in this.section) {
        if (Object.hasOwnProperty.call(this.section, key)) {
          this.section[key].active = false;
        }
      }
      this.section[index].active = true;
      // console.log(this.section[index]);
      console.log(this.section);
    }
  }
};
</script>

<style lang="scss">
.process__wraper {
  margin: 70px 0 30px;
  flex-shrink: 0;
}
.process {
  background: black;
  width: 100%x;
  height: 100%;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 80px;
  padding: 30px 10px;
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  position: relative;
  z-index: 0;
  &__bar {
    position: absolute;
    top: 40px;
    left: 50px;
    width: 90%;
    height: 10px;
    background-color: #fff;
    z-index: -1;
  }
  &__position {
    display: flex;
    align-items: center;
    flex-direction: column;
    width: 100px;
  }
  &__dot {
    box-sizing: border-box;
    width: 30px;
    height: 30px;
    margin: 0 0 15px;
    background-color: white;
    border: 7px solid white;
    border-radius: 50%;
    cursor: pointer;
    &.process__dot--active {
      background-color: #ffe713;
    }
  }
  &__info {
    text-align: center;
    color: white;
    cursor: pointer;
  }
}
</style>
