<template>
  <section class="body-mass-index">
    <div class="container">
      <div class="body-mass-index__inner">
        <h2 class="main__text">
          Индекс массы тела
          <Question :description="description" />
        </h2>
        <div class="inner-wrapper body-mass-index__button__wrapper">
          <ButtonBack />
          <div class="body-mass-index__button__inner">
            <IndexCalendar />
            <IndexHeight />
            <IndexWeight />
          </div>
          <Help />
        </div>
        <div class="body-figure">
          <div class="body-figure__diagram">
            <span class="body-figure__waight">25.3</span>
          </div>
          <div class="body-figure__descr">
            <img
              class="body-figure__descr--img"
              src="@/assets/images/body-figure/inadequate-weight.svg"
              alt="фигура недостаточный вес"
            />
            <div class="body-figure__descr--text">Недостаточный вес</div>
          </div>
          <ButtonNext />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import ButtonBack from "@/components/repeat/ButtonBack.vue";
import ButtonNext from "@/components/repeat/ButtonNext.vue";
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
    ButtonNext,
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

.body-figure {
  margin: -80px auto 50px;
  max-width: 650px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.body-figure__diagram {
  width: 140px;
  height: 140px;
  border-radius: 50%;
  border: 15px solid $btn-color;

  display: flex;
  align-items: center;
  justify-content: center;
}
.body-figure__waight {
  font-family: "Roboto Condensed", sans-serif;
  font-style: normal;
  font-weight: bold;
  font-size: 3rem;
  line-height: 3rem;
  color: $yellow;
}
.body-figure__descr {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 230px;
}
.body-figure__descr--img {
}
.body-figure__descr--text {
  font-family: "Roboto Condensed", sans-serif;
  font-style: normal;
  font-weight: bold;
  font-size: 1.3333rem;
  line-height: 1.3889rem;
  max-width: 165px;
  text-align: left;
  /* or 104% */
  color: $white;
}
</style>
