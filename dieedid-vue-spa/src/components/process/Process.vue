<template>
  <section class="process__wraper">
    <div class="container">
      <div class="process">
        <div class="process__bar"></div>
        <div class="process__position" v-for="name in section" :key="name">
          <div class="process__dot"></div>
          <div class="process__info">
            {{ name }}
          </div>
        </div>
      </div>
    </div>
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
.process__wraper{
flex-shrink: 0;
}
.process {
  
  background: black;
  width: 100%x;
  height: 100%;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 80px;
  padding: 30px 10px;
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  position: relative;
  z-index: 0;
  &__bar {
    position: absolute;
    top: 40px;
    left: 50px;
    width: 90%;
    height: 10px;
    background-color: #fff;
    z-index: -1;
  }
  &__position {
    display: flex;
    align-items: center;
    flex-direction: column;
    width: 100px;
  }
  &__dot {
    box-sizing: border-box;
    width: 30px;
    height: 30px;
    margin: 0 0 15px;
    background-color: #ffe713;
    border: 7px solid white;
    border-radius: 50%;
    cursor: pointer;
  }
  &__info {
    text-align: center;
    color: white;
    cursor: pointer;
  }
}
</style>
