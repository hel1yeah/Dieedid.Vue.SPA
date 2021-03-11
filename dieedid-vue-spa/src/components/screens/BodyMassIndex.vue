<template>
  <section class="body-mass-index">
    <div class="container">
      <div class="body-mass-index__inner">
        <h2 class="main__text">
          Индекс массы тела
          <Question :description="description" />
        </h2>
        <div class="body-mass-index-button--wrapper">
          <ButtonBack />
          <div class="body-mass-index--buttons"></div>
          <div class="body-mass-index--buttons"></div>
          <div class="body-mass-index--buttons"></div>
          <Calendar />
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
import Calendar from "@/components/calendar/Calendar.vue";

export default {
  name: "BodyMassIndex",
  components: {
    Question,
    Calendar,
    ButtonBack,
    Help
  },
  data() {
    return {
      description:
        "Индекс массы тела - величина, позволяющая оценить степень соответствия массы человека и его роста и тем самым косвенно судить о том, является ли масса недостаточной, нормальной или избыточной. Важен при определении показаний для необходимости лечения."
    };
  }
};
</script>

<style lang="scss"></style>
