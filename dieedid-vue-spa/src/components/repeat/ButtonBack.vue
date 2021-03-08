<template>
  <button class="button-back">
    <svg class="button-back__img">
      <use xlink:href="../../assets/images/sprite/sprite.svg#arrow-back"></use>
    </svg>
    <div class="button-back__text">
      Назад
    </div>
  </button>
</template>

<script>
export default {
  name: "ButtonBack",
  data() {
    return {};
  }
};
</script>

<style lang="scss">
.button-back {
  color: $gold;
  border: 1px solid $gold;
  border-radius: 25px;
  width: 140px;
  height: 50px;
  background-color: transparent;
  text-transform: lowercase;
  margin: auto 0 40px;

  display: flex;
  align-items: center;
  justify-content: center;

  cursor: pointer;
  &:active,
  &:focus {
    outline: transparent;
  }
  &__img {
    width: 22px;
    height: 20px;
  }
  &__text {
    font-family: Roboto Condensed;
    font-style: normal;
    font-weight: 300;
    font-size: 1.3333rem;
    color: $gold;
    padding: 0 0 5px 10px;
  }
}
</style>
