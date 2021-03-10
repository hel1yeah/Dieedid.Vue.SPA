<template>
  <section class="physical__exercise">
    <div class="container">
      <div class="physical__exercise--inner">
        <h2 class="main__text">
          Физические нагрузки
          <Question />
        </h2>
        <div class="physical__exercise-button--wrapper">
          <ButtonBack />
          <div class="physical__exercise--buttons">
            <div
              v-for="(act, index) in xercise"
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
  name: "PhysicalExercise",
  components: {
    ButtonBack,
    Help,
    Question
  },
  data() {
    return {
      xercise: {
        minimum: {
          name: "минимумили полное отсутствие",
          active: false,
          id: 1
        },
        small: {
          name: "небольшое 1-3 раза в неделю",
          active: false,
          id: 2
        },
        normal: { name: "3-5 раз в неделю", active: false, id: 3 },
        everyday: { name: "каждый день", active: false, id: 4 }
      },
      description:
        "Ваш образ жизни существенное влияет на количество пищи, включенной в вашу индивидуальную программу питания. Если вы не можете найти точный ответ, выберите тот, который наиболее точно соответствует вашему типичному дню."
    };
  }
};
</script>

<style lang="scss">
.physical__exercise {
  &--inner {
    background-image: url("./../../assets/images/man-woman.png");
    background-position: center center;
    background-size: contain;
    background-repeat: no-repeat;
  }
  &--buttons {
    width: 800px;
    margin: 0 0 90px;
  }
}
.physical__exercise-button--wrapper {
  display: flex;
  justify-content: space-between;
  padding: 0 30px;
}
</style>
