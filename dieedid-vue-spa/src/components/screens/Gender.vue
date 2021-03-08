<template>
  <section class="gender">
    <div class="container">
      <div class="gender__inner">
        <div class="gender__inner--header">
          <h1 class="heading">
            Персональная кето диета на 28 дней!
          </h1>
          <div class="gender__selection">
            <p>Выбери свой пол</p>
            <div class="btn__wrapper">
              <button class="btn-gender btn-gender--male">
                <img
                  src="@/assets/images/gender-male.svg"
                  alt="gender-male-img"
                />
              </button>
              <button class="btn-gender btn-gender--female">
                <img
                  src="@/assets/images/gender-female.svg"
                  alt="gender-male-img"
                />
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Gender"
};
</script>

<style lang="scss">
.gender {
  margin: 42px 0 42px;
  z-index: 0;
  &__inner {
    display: flex;
    justify-content: flex-start;
    position: relative;
    // z-index: 0;
    &::before {
      content: "";
      position: absolute;
      width: 840px;
      height: 690px;
      top: -27px;
      left: 28%;
      background-image: url("../../assets/images/woman-salad.png");
      background-size: contain;
      // z-index: -1;
    }
    &--header {
    }
  }
}
.heading {
  max-width: 570px;
  font-family: "Roboto Condensed", sans-serif;
  font-size: 4.1667rem;
  font-style: normal;
  font-weight: 700;
  line-height: 4.7222rem;
  text-align: left;
  text-transform: uppercase;
  color: $gold;
}

.gender__selection {
  max-width: 450px;
  margin: 57px 0 0;
  & p {
    font-family: "Roboto Condensed", sans-serif;
    font-size: 1.7778rem;
    font-style: normal;
    font-weight: 400;
    line-height: 2.1111rem;
    text-align: center;
    text-transform: uppercase;
    margin: 0 0 15px;
  }
}
.btn__wrapper {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.btn-gender {
  width: 210px;
  height: 210px;
  border-radius: 50%;
  border: none;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  z-index: 2;
  &:active,
  &:focus {
    outline: transparent;
  }
}
.btn-gender--male {
  background: linear-gradient(180deg, #4383be 0%, #2b56a9 100%);
}
.btn-gender--female {
  background: linear-gradient(180deg, #c879ca 0%, #ae04b1 100%);
}
</style>
