<template>
  <section class="body-mass-index">
    <div class="container">
      <div class="body-mass-index__inner">
        <h2 class="main__text">
          Индекс массы тела
          <Question :description="description" />
        </h2>
        <div class="body-mass-index__button__wrapper">
          <ButtonBack />
          <div class="body-mass-index__button__inner">
            <IndexCalendar />
            <IndexHeight />
            <IndexWeight />
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
import IndexCalendar from "@/components/BodyMassIndexButtons/IndexCalendar.vue";
import IndexHeight from "@/components/BodyMassIndexButtons/IndexHeight.vue";
import IndexWeight from "@/components/BodyMassIndexButtons/IndexWeight.vue";

export default {
  name: "BodyMassIndex",
  components: {
    Question,
    Help,
    ButtonBack,
    IndexCalendar,
    IndexHeight,
    IndexWeight
  },
  data() {
    return {
      inputData: "21-03-13",
      description:
        "Индекс массы тела - величина, позволяющая оценить степень соответствия массы человека и его роста и тем самым косвенно судить о том, является ли масса недостаточной, нормальной или избыточной. Важен при определении показаний для необходимости лечения."
    };
  }
};
</script>

<style lang="scss">
.body-mass-index {
  &__inner {
    width: 100%;
    text-align: center;
  }
  &__buttons {
    display: flex;
    justify-content: flex-start;
    align-items: center;
  }
  &__button__wrapper {
    display: flex;
    justify-content: space-between;
  }
  &__button__inner {
    width: 800px;
    margin: 0 0 90px;
  }
}
.body-mass-index--buttons {
  border-radius: 25px;
}
.calendar__img {
  width: 63px;
  height: 65px;
  padding: 10px;
  margin: 0 100px 0 0;
}
</style>
