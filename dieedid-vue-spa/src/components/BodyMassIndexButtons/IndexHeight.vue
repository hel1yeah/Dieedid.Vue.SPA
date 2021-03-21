<template>
  <div
    class="activity--button index-height"
    @click="showModalHeight = !showModalHeight"
  >
    <div class="height__inner">
      <svg class="height__icon">
        <use xlink:href="../../assets/images/sprite/sprite.svg#height"></use>
      </svg>
      <span class="index-height__number">{{ height }}</span>
    </div>
    <span class="index-height__unit">см.</span>
    <div class="height__position" v-if="showModalHeight">
      <div class="height__modal">
        <ul class="modal__list">
          <li
            class="modal__list--item"
            :class="{ 'list__item-active': item === height }"
            v-for="(item, index) in numbersHeight"
            :key="index"
            @click.stop="itemSelection(item)"
          >
            {{ item }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "IndexHeight",
  data() {
    return {
      showModalHeight: false,
      numbersHeight: [],
      height: "рост"
    };
  },
  methods: {
    itemSelection(item) {
      this.height = item;
      this.showModalHeight = !this.showModalHeight;
    }
  },
  mounted() {
    // добавляем рост
    for (let i = 130; i <= 220; i++) {
      this.numbersHeight.push(i);
    }

    document.addEventListener("click", event => {
      if (
        !event.target.classList.contains("activity--button", "index-height")
      ) {
        this.showModalHeight = false;
      }
    });
  }
};
</script>

<style lang="scss">
.index-height {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: space-between;
  color: $hover-btn-color;
  font-weight: normal;
  text-transform: lowercase;
}
.index-height:hover .height__icon {
  fill: $white;
}
.height__inner {
  display: flex;
  align-items: center;
  pointer-events: none;
}

.height__icon {
  width: 42px;
  height: 42px;
  margin: 0 40px 0 0;
  fill: $hover-btn-color;
  transition: 0.2s;
  &:hover {
    fill: $white;
  }
}
.index-height__number {
  &:first-letter {
    text-transform: uppercase;
  }
}
.index-height__unit {
   pointer-events: none;
  font-weight: 700;
}
.height__position {
  background-color: $white;
  border-radius: 10px;
  overflow: hidden;
  position: absolute;
  left: -200px;

  color: $hover-btn-color;
}
.height__modal {
  overflow: auto;
  width: 180px;
  height: 300px;
}

.modal__list--item {
  color: $black;
  margin: 5px 0;
  list-style-type: none;
  font-size: 1.2rem;

  &:hover {
    background-color: $grey;
  }
}

.list__item-active {
  color: $hover-btn-color;
  font-size: 1.6rem;
}

.height__modal::-webkit-scrollbar {
  width: 10px;
  background-color: $grey;
}
.height__modal::-webkit-scrollbar-track {
  -webkit-box-shadow: 5px 5px 5px -5px rgba(34, 60, 80, 0.2) inset;
  background-color: #f9f9fd;
}
.height__modal::-webkit-scrollbar-thumb {
  background-color: $btn-color;
  border-radius: 5px;
  &:hover {
    background-color: $hover-btn-color;
  }
}
</style>
