<template>
  <section class="physical__activity">
    <div class="container">
      <h2 class="physical__activity--title">Физическая активность</h2>
      <p class="physical__activity--descr">Исключая тренировки</p>
      <div class="physical__activity-button--wrapper">
        <ButtonBack />
        <button></button>
        <a href="">asdasdasdsad</a>
      </div>
    </div>
  </section>
</template>

<script>
import ButtonBack from "@/components/repeat/ButtonBack.vue";
export default {
  name: "PhysicalActivity",
  components: {
    ButtonBack
  }
};
</script>
