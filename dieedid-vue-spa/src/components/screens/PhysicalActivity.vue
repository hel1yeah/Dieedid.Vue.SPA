<template>
  <section class="physical__activity">
    <div class="container">
      <div class="physical__activity--inner">
        <h2 class="main__text">
          Физическая активность
          <Question :description="description" />
        </h2>
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
          id: 1
        },
        heavy: { name: "тяжёлый физический труд", active: false, id: 1 }
      },
      description:
        "Ваш образ жизни существенное влияет на количество пищи, включенной в вашу индивидуальную программу питания. Если вы не можете найти точный ответ, выберите тот, который наиболее точно соответствует вашему типичному дню."
    };
  }
};
</script>

<style lang="scss">
.physical__activity {
  font-family: "Roboto Condensed";
  text-align: center;
  color: $gold;
  text-transform: uppercase;

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
  display: flex;
  justify-content: space-between;
  padding: 0 30px;
}
.physical__activity--buttons {
  width: 800px;
  margin: 0 0 90px;
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
.main__text {
  display: inline-block;
  font-size: 4.0556rem;
  margin: 0 auto 20px;
  position: relative;
}
</style>
