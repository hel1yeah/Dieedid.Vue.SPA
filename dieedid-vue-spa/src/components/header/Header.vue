<template>
  <header class="header">
    <router-link to="/">
      <svg class="header__logo-dieedid">
        <use
          xlink:href="../../assets/images/sprite/sprite.svg#logo-dieedid"
        ></use>
      </svg>
    </router-link>

    <button class="header__button">ОТКРЫТЬ МОЮ ПРОГРАММУ</button>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style lang="scss">
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  transition: 1s;
  &__logo-dieedid {
    fill: #44af5c;
    width: 105px;
    height: 68px;
  }
  &__button {
    height: 45px;
    width: 205px;
    border-radius: 20px;
    border: transparent;
    color: white;
    background: linear-gradient(180deg, #04c44c 0%, #20c05c 100%);
    cursor: pointer;
    font-family: "Roboto Condensed";
    font-style: normal;
    font-weight: bold;
    font-size: 0, 7222rem;
    transition: all 0.8s ease;
    &:hover {
      background: linear-gradient(180deg, #0da847 0%, #109742 100%);
      transition: all 2s ease 0s;
    }
  }
}
</style>