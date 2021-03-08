<template>
  <div class="help-back">
    <svg class="help-back__img">
      <use xlink:href="../../assets/images/sprite/sprite.svg#question"></use>
    </svg>
    <div class="help-back__text">
      Help
    </div>
  </div>
</template>

<script>
export default {
  name: "Help",
  data() {
    return {};
  }
};
</script>

<style lang="scss">
.help-back {
  color: $gold;
  border: 1px solid $gold;
  border-radius: 15px;
  width: 130px;
  height: 50px;
  background-color: transparent;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: auto 0 40px;
  background: rgba(26, 23, 23, 0.5);

  cursor: pointer;
  &:active,
  &:focus {
    outline: transparent;
  }
  &__img {
    width: 36px;
    height: 36px;
  }
  &__text {
    font-family: "Roboto", sans-serif;
    font-style: normal;
    font-weight: 300;
    font-size: 1.7222rem;
    color: $gold;
    padding: 0 0 5px 10px;
    text-transform: lowercase;
    &:first-letter {
      text-transform: uppercase;
    }
  }
}
</style>
