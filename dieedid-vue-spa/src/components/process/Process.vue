<template>
  <section class="process">
    <!-- <div class="process__position" v-for="name in section" :key="name">
      <div class="process__dot">
        <div class="process__dot--inner"></div>
      </div>
      <div class="process__info">
        {{ name }}
      </div>
    </div> -->
  </section>
</template>

<script>
export default {
  name: "Process",
  data() {
    return {
      section: [
        "Пол",
        "Физическая активность",
        "Физические нагрузки",
        "Индексы массы тела",
        "Аллергия",
        "Личные  данные",
        "Сводка"
      ]
    };
  }
};
</script>

<style lang="scss">
* {
  box-sizing: border-box;
}

.process {
  background: black;
  width: 1100px;
  height: 100%;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 80px;
  padding: 30px 10px;
  display: flex;
  align-items: flex-start;
  justify-content: space-between;

  &__position {
    position: relative;
    display: flex;
    align-items: center;
    flex-direction: column;
    width: 100px;
  }
  &__dot {
    position: relative;
    box-sizing: border-box;
    width: 30px;
    height: 30px;
    margin: 0 0 15px;

    &:before {
      content: "";
      position: absolute;
      top: 50%;
      left: 0;
      transform: translateY(-50%);
      background-color: #fff;
      border: 1px solid red;
      width: 150px;
      height: 10px;
    }
    &--inner {
      position: relative;
      z-index: 5;
      width: 30px;
      height: 30px;
      background-color: yellow;
      border-radius: 50%;
      border: 7px solid white;
    }
  }
  &__info {
    text-align: center;
    color: white;
  }
}
</style>
