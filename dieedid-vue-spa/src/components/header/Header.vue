<template>
  <header class="header__section">
    <div class="container">
      <div class="header">
        <router-link to="#">
          <svg class="header__logo-dieedid">
            <use
              xlink:href="@/assets/images/sprite/sprite.svg#logo-dieedid"
            ></use>
          </svg>
        </router-link>
        <button class="header__button">ОТКРЫТЬ МОЮ ПРОГРАММУ</button>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style lang="scss">
.header__section {
  margin: 34px 0 0;
}
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  // margin: 35px 0 0;
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
    color: &white;
    background: #20c05c;
    cursor: pointer;
    outline: transparent;
    font: {
      family: "Roboto Condensed";
      style: normal;
      weight: bold;
      size: 0.7222rem;
    }
    transition: 1s;
    &:hover {
      background: $hover-btn-color;
    }
    &:active,
    &:focus {
      background: rgba(9, 122, 51, 1);
    }
  }
}
</style>
