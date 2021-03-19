<template>
  <div class="activity--button index-weight">
    <div class="weight__inner">
      <svg class="weight__icon">
        <use
          xlink:href="../../assets/images/sprite/sprite.svg#weighingSale"
        ></use>
      </svg>
      <span class="index-weight__number">Вес</span>
    </div>

    <span class="index-weight__unit">см.</span>
  </div>
</template>

<script>
export default {
  name: "IndexWeight"
};
</script>

<style lang="scss">
.index-weight {
  display: flex;
  align-items: center;
  justify-content: space-between;
  color: $hover-btn-color;
  font-weight: normal;
  text-transform: lowercase;
}
.index-weight:hover .weight__icon {
  fill: $white;
}
.weight__inner {
  display: flex;
  align-items: center;
}

.weight__icon {
  width: 42px;
  height: 42px;
  margin: 0 40px 0 0;
  fill: $hover-btn-color;
  transition: 0.2s;
  &:hover {
    fill: $white;
  }
}
.index-weight__number {
  &:first-letter {
    text-transform: uppercase;
  }
}
.index-weight__unit {
  // text-transform: uppercase;
  font-weight: 700;
}
</style>
