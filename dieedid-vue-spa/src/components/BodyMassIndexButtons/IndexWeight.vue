<template>
  <div
    class="activity--button index-weight"
    @click="showModalWeight = !showModalWeight"
  >
    <div class="weight__inner">
      <svg class="weight__icon">
        <use
          xlink:href="../../assets/images/sprite/sprite.svg#weighingSale"
        ></use>
      </svg>
      <span class="index-weight__number">{{ weight }}</span>
    </div>

    <span class="index-weight__unit">кг.</span>

    <div class="weight__position" v-if="showModalWeight">
      <div class="weight__modal">
        <ul class="modal__list">
          <li
            class="modal__list--item"
            :class="{ 'list__item-active': item === weight }"
            v-for="(item, index) in numberWeight"
            :key="index"
            @click="itemSelection(item)"
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
  name: "IndexWeight",
  data() {
    return {
      showModalWeight: false,
      numberWeight: [],
      weight: "вес"
    };
  },
  methods: {
    itemSelection(item) {
      this.weight = item;
      this.showModalWeight = !this.showModalWeight;
    },
    closeModal() {
      this.showModalWeight = false;
    }
  },
  mounted() {
    for (let i = 40; i <= 200; i++) {
      this.numberWeight.push(i);
    }
    document.addEventListener("click", event => {
      if (!event.target.classList.contains("index-weight")) {
        this.showModalWeight = false;
      }
    });
  }
};
</script>

<style lang="scss">
.index-weight {
  position: relative;
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
  pointer-events: none;
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
  pointer-events: none;
  font-weight: 700;
}
.weight__position {
  background-color: $white;
  border-radius: 10px;
  overflow: hidden;
  position: absolute;
  left: -200px;

  color: $hover-btn-color;
}
.weight__modal {
  overflow: auto;
  width: 180px;
  height: 300px;
}

.modal__list--item {
  color: $black-gray;
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

.weight__modal::-webkit-scrollbar {
  width: 10px;
  background-color: $grey;
}
.weight__modal::-webkit-scrollbar-track {
  -webkit-box-shadow: 5px 5px 5px -5px rgba(34, 60, 80, 0.2) inset;
  background-color: #f9f9fd;
}
.weight__modal::-webkit-scrollbar-thumb {
  background-color: $btn-color;
  border-radius: 5px;
  &:hover {
    background-color: $hover-btn-color;
  }
}
</style>
