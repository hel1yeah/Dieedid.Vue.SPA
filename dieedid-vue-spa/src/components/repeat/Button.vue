<template>
  <button
    class="v-button"
    v-bind:style="{
      width: this.width,
      height: this.height,
      color: this.color,
      fontSize: this.fontSize,
      fontWeight: this.fontWeight,
      textTransform: this.textTransform,
      backgroundColor: this.backgroundColor,
      border: this.border,
      borderColor: this.borderColor,
      borderRadius: this.borderRadius,
      borderStyle: this.borderColor,
      borderWidth: this.borderWidth,
      cursor: this.cursor
    }"
  >
    <div class="v-button-body">
      <div
        class="v-button-icon"
        v-bind:style="{
          width: this.iconWidth,
          height: this.iconHeight,
        }"
      >
        <slot name="icon" />
      </div>
      <slot name="label">Текст</slot>
    </div>
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    width: String,
    height: String,
    color: String,
    fontSize: String,
    textTransform: String,
    fontWeight: String,
    backgroundColor: String,
    border: String,
    borderRadius: String,
    borderColor: String,
    borderWidth: String,
    borderStyle: String,
    iconWidth: String,
    iconHeight: String,
    cursor: {
      type: String,
      default: "pointer"
    }
  }
};
</script>

<style lang="scss" scoped>
.v-button:focus {
  outline: none;
}
.v-button-body {
  display: flex;
  justify-content: center;
  align-items: center;
}
.v-button-icon {
  margin-right: 10px;
}
.v-button-icon > * {
  width: 100%;
  height: 100%;
}
</style>
