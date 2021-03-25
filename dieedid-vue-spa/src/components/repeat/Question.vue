<template>
  <div class="question__position">
    <div class="question" @click.stop="descriptionShow">
      <svg class="help__img">
        <use xlink:href="../../assets/images/sprite/sprite.svg#question"></use>
      </svg>
      <div class="question__description" v-show="this.descriptionInfo">
        {{ description }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Question",
  props: {
    description: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      descriptionInfo: false
    };
  },
  methods: {
    descriptionShow() {
      this.descriptionInfo = !this.descriptionInfo;
    }
  }
};
</script>
<style lang="scss">
.question {
  width: 36px;
  height: 36px;
  position: relative;
  display: flex;
  cursor: pointer;
  border-radius: 50%;
  transition: $transition;
  z-index: 333;
  &:hover {
    box-shadow: $shadow;
  }
  &__position {
    position: absolute;
    top: -11px;
    right: -35px;
  }
  &__description {
    position: absolute;
    top: 45px;
    right: 50%;
    transform: translateX(50%);
    color: #000;
    font-family: "Roboto Condensed", sans-serif;
    font-size: 0.8889rem;
    line-height: 1rem;
    transition: all 1s ease-out;

    width: 385px;
    padding: 25px 27px;
    background-color: $white;
    border-radius: 15px;
    font-weight: normal;

    text-transform: lowercase;

    box-shadow: 0px 0px 34px 16px rgba(34, 60, 80, 0.2);
    &:first-letter {
      text-transform: uppercase;
    }
  }
}
</style>
