<template>
  <section class="physical__activity">
    <div class="container">
      <div class="physical__activity--inner">
        <h2 class="main__text">
          Физическая активность
          <Question :description="description" />
        </h2>
        <p class="physical__activity--descr">Исключая тренировки</p>
        <div class="inner-wrapper physical__activity-button--wrapper">
          <ButtonBack />
          <div class="physical__activity--buttons">
            <div
              v-for="(act, index) in activity"
              :key="index"
              class="activity--button"
            >
              {{ act.name }}
            </div>
          </div>
          <Help />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import ButtonBack from "@/components/repeat/ButtonBack.vue";
import Help from "@/components/repeat/Help.vue";
import Question from "@/components/repeat/Question.vue";

export default {
  name: "PhysicalActivity",
  components: {
    ButtonBack,
    Help,
    Question
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
          id: 2
        },
        heavy: { name: "тяжёлый физический труд", active: false, id: 3 }
      },
      description:
        "Ваш образ жизни существенное влияет на количество пищи, включенной в вашу индивидуальную программу питания. Если вы не можете найти точный ответ, выберите тот, который наиболее точно соответствует вашему типичному дню."
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
  margin: 30px 0 -10px;

  &--inner {
    background-image: url("./../../assets/images/physical-activity.png");
    background-position: bottom right;
    background-size: contain;
    background-repeat: no-repeat;
  }

  &--descr {
    font-size: 1.3333rem;
    margin: 0 0 55px;
  }
}
.physical__activity-button--wrapper {
}
.physical__activity--buttons {
  width: 800px;
  margin: 0 0 90px;
}
</style>
