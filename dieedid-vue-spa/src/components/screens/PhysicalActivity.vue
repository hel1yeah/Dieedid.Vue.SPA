<template>
  <section class="physical__activity">
    <div class="container">
      <div class="physical__activity--inner">
        <h2 class="physical__activity--title">Физическая активность</h2>
        <p class="physical__activity--descr">Исключая тренировки</p>
        <div class="physical__activity-button--wrapper">

          <ButtonBack />
          <div class="physical__activity--buttons">
            <div
              v-for="(act, index) in activity"
              :key="index"
              class="activity--button"
              :class="{ btnActive: act.active }"
            >
              {{ act.name }}
            </div>
          </div>

          <Help />

        </div>
      </div>
    </div>
    
    <!--  ОДИН И ТОТ ЖЕ КОМПОНЕНТ, НО С РАЗНЫМИ ПРОПСАМИ   -->
    <!--  ПОСМОТРИШЬ, МОЖНО ЛИ ТАК ПИСАТЬ В САМОМ VUE, ИЛИ ЛЕДУЕТ ДУБЛИРОВАТЬ PROPS В DATA() {}  -->
    <!--  ПОСКОЛЬКУ Я ДАВНО НЕ ПИСАЛ НА VUE, ДАЖЕ ОЧЕНЬ ДАВНО  -->
    <div style="display: flex; margin: 20px; justify-content: center">
      <!--  ПЕРВЫЙ КОМПОНЕНТ  -->
      <Button
        width="140px"
        height="50px"
        color="#fff599"
        font-size="1.3333rem"
        background-color="transparent"
        text-transform="lowercase"
        border-radius="25px"
        border="1px solid #fff599"
        icon-height="22px"
        icon-width="22px"
      >
        <svg class="button-back__img" slot="icon">
          <use xlink:href="../../assets/images/sprite/sprite.svg#arrow-back"></use>
        </svg>
        <span slot="label">назад</span>
      </Button>

      <!--  ВТОРОЙ КОМПОНЕНТ  -->
      <Button
        width="130px"
        height="50px"
        color="#fff599"
        font-size="1.7222rem"
        background-color="rgba(26, 23, 23, 0.5)"
        border-radius="15px"
        border="1px solid #fff599"
        icon-height="36px"
        icon-width="36px"
      >
        <svg class="button-back__img" slot="icon">
          <use xlink:href="../../assets/images/sprite/sprite.svg#question"></use>
        </svg>
        <span slot="label">Help</span>
      </Button>
    </div>
  </section>
</template>

<script>
import ButtonBack from "@/components/repeat/ButtonBack.vue";
import Help from "@/components/repeat/Help.vue";
import Button from "@/components/repeat/Button";

export default {
  name: "PhysicalActivity",
  components: {
    Button,
    ButtonBack,
    Help
  },
  data() {
    return {
      activity: {
        sedentaryWork: {
          name: "работа в офисе / сижу дома",
          active: false,
          id: 1
        },
        walks: {
          name: "лёгкий физический труд / частые прогулки",
          active: false,
          id: 1
        },
        heavy: { name: "тяжёлый физический труд", active: false, id: 1 }
      }
    };
  }
};
</script>

<style lang="scss">
.physical__activity {
  font-family: "Roboto Condensed", sans-serif;
  text-align: center;
  color: $gold;
  text-transform: uppercase;

  &--inner {
    background-image: url("./../../assets/images/physical-activity.png");
    background-position: bottom right;
    background-size: contain;
    background-repeat: no-repeat;
  }

  &--title {
    font-size: 4.0556rem;
    margin: 0 0 20px;
  }

  &--descr {
    font-size: 1.3333rem;
    margin: 0 0 55px;
  }
}

.physical__activity-button--wrapper {
  display: flex;
  justify-content: space-between;
  padding: 0 30px;
}

.physical__activity--buttons {
  width: 800px;
}

.activity--button {
  color: $active-btn-color;
  background-color: $white;
  border-radius: 25px;
  padding: 25px 0;
  margin: 0 0 40px;
  width: 100%;
  text-transform: uppercase;

  font-family: "Roboto Condensed", sans-serif;
  font-weight: 800;
  font-size: 1.6667rem;
  line-height: 2.2222rem;

  &:hover {
    background-color: $hover-btn-color;
    color: $white;
  }
}
</style>
