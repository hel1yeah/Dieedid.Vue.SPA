<template>
  <section class="objective">
    <div class="container">
      <h2 class="main__text">
        Цели
        <Question :description="description" />
      </h2>
      <div class="objective__inner">
        <div class="objective__diet">
          <div class="objective__diet--header">
            Цель диеты
          </div>
          <div
            class="objective__diet--item"
            v-for="object in objectiveDiet"
            :key="object"
          >
            {{ object.name }}
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Question from "@/components/repeat/Question.vue";
export default {
  name: "Objective",
  components: {
    Question
  },
  data() {
    return {
      objectiveDiet: {
        slimming: {
          name: "похудение",
          check: false
        },
        gain: {
          name: "набор мышечной массы",
          check: true
        },
        save: {
          name: "удержание веса",
          check: false
        }
      },
      description:
        "Худеть нужно с целью. Самое главное - чтобы цель была реальной, например, брюки на пару размеров меньше, или участие в марафоне. Определив, чего ты хочешь достичь, разбей свой путь к цели на этапы. Для начала можно исключить из рациона питания определенные продукты, которые вредны для твоего веса."
    };
  }
};
</script>

<style lang="scss">
.objective {
  text-align: center;
  color: $black;
}
.objective__inner {
  margin: 0 auto;
  width: 900px;
}
.objective__diet {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.objective__diet--header {
  color: $gold;
  font-weight: 700;
}
.objective__diet--item {
  padding: 12px 25px;
  text-transform: uppercase;
  background-color: $white;
  border-radius: 10px;
}
</style>
