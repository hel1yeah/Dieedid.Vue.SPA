<template>
  <section class="allergy">
    <div class="container">
      <h2 class="main__text">
        Аллергия
        <Question :description="description" />
      </h2>
      <div class="allergy__check">
        <p class="allergy__check--true">Включить</p>
        <span>/</span>
        <p class="allergy__check--false">Исключить</p>
      </div>
      <div class="inner-wrapper allergy__button__wrapper">
        <ButtonBack />
        <div class="allergy-product ">
          <div
            class="allergy-product__item "
            v-for="(allergy, index) in allergyList"
            :key="index"
            @click="excludeFood(allergy)"
            :class="{ 'allergy-product__item--false': allergy.allergy }"
          >
            <div class="allergy-product__false" v-show="allergy.allergy"></div>
            <img
              class="allergy-product__item--img"
              :src="allergy.img"
              alt="mile"
            />
            <span class="allergy-product__item--text">{{ allergy.name }}</span>
            <div class="allergy-product__choice">
              <img
                v-if="allergy.allergy === false"
                class="choice__true"
                src="../../assets/images/allergy/checking-mark-ok.svg"
                alt="true"
              />
              <img
                v-if="allergy.allergy"
                class="choice__false"
                src="../../assets/images/allergy/cheking-mark-not-ok.svg"
                alt="false"
              />
            </div>
          </div>
        </div>
        <Help />
      </div>
      <div class="individual-products">
        <div class="individual-products__text">
          Исключить отдельные продукты
        </div>
        <div class="individual-products__wrapper-selector">
          <div class="individual-products__selector">
            <multiselect
              class="products__selector"
              v-model="value"
              :options="options"
              :hide-selected="true"
              :multiple="true"
              :close-on-select="true"
              :searchable="true"
              placeholder="Какие продукты исключить ?"
              tag-placeholder="Добавить свой продукт"
              :taggable="true"
              @tag="addTag"
            >
              <span slot="noResult"> Таких продуктов нету </span>
            </multiselect>
          </div>
          <div class="individual-products__selector-choice">
            <div class="individual-products__tag-wrap">
              <div
                class="individual-products__tag"
                v-for="item in value"
                :key="item"
              >
                <span>
                  {{ item }}
                </span>
                <span @click="removeTag(item)"></span>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="allergy__button-next-wrapper">
        <ButtonNext />
      </div>
    </div>
  </section>
</template>

<script>
import Multiselect from "vue-multiselect";

import ButtonBack from "@/components/repeat/ButtonBack.vue";
import ButtonNext from "@/components/repeat/ButtonNext.vue";
import Help from "@/components/repeat/Help.vue";
import Question from "@/components/repeat/Question.vue";
export default {
  name: "Allergy",
  components: {
    Multiselect,
    ButtonBack,
    ButtonNext,
    Help,
    Question
  },
  data() {
    return {
      value: [],
      options: [
        "грецкий орех",
        "морковь",
        "мед",
        "лесной орех",
        "кокос",
        "бразильский орех"
      ],
      allergyList: {
        not: {
          // img: "../../assets/images/allergy/smile.svg",
          img: require("../../assets/images/allergy/smile.svg"),
          name: "нет",
          id: 1,
          allergy: false
        },
        gluten: {
          img: require("../../assets/images/allergy/gluten.svg"),
          name: "глютен",
          id: 2,
          allergy: true
        },
        lactose: {
          img: require("../../assets/images/allergy/lactose.svg"),
          name: "лактоза",
          id: 3,
          allergy: false
        },
        eggs: {
          img: require("../../assets/images/allergy/eggs.svg"),
          name: "яйца",
          id: 4,
          allergy: false
        },
        fish: {
          img: require("../../assets/images/allergy/fish.svg"),
          name: "рыба",
          id: 5,
          allergy: false
        },
        seafood: {
          img: require("../../assets/images/allergy/seafood.svg"),
          name: `море- продукты`,
          id: 6,
          allergy: false
        },
        soy: {
          img: require("../../assets/images/allergy/soy.svg"),
          name: "соя",
          id: 7,
          allergy: false
        },
        cashew: {
          img: require("../../assets/images/allergy/cashew.svg"),
          name: "орехи и сметана",
          id: 8,
          allergy: false
        },
        honey: {
          img: require("../../assets/images/allergy/honey.svg"),
          name: "мёд",
          id: 9,
          allergy: false
        },
        milk: {
          img: require("../../assets/images/allergy/milk.svg"),
          name: "Коровье молоко",
          id: 10,
          allergy: false
        }
      },
      exclude: [],
      description:
        "Аллергия − это хроническое заболевание, вызванное неадекватной, нежелательной и неожиданной реакцией иммунной системы на воздействие веществ, которые обычно не приводят к заболеванию и не наносят вред человеку, например: на продукты питания, лекарства, пыльцу растений, яд насекомых и др."
    };
  },
  methods: {
    excludeFood(allergy) {
      allergy.allergy = !allergy.allergy;
    },
    addTag(newTag) {
      const tag = newTag.toLowerCase().trim();
      this.options.push(tag);
      this.value.push(tag);
    },
    removeTag(item) {
      let res = this.value.filter(filtersTags);
      function filtersTags(elem) {
        if (elem !== item) {
          return true;
        }
        return false;
      }
      this.value = res;
    }
  }
};
</script>

<style lang="scss">
.allergy {
  text-align: center;
  margin: 30px 0 60px;
}
.allergy__check {
  font-family: "Roboto Condensed", sans-serif;
  font-style: normal;
  font-weight: normal;
  font-size: 1.9444rem;
  line-height: 2.5rem;

  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;

  margin: 0 0 25px;
  & span {
    padding: 0 5px;
    color: $hover-btn-color;
  }
}
.allergy__check--true {
  color: $hover-btn-color;
  position: relative;
  &::before {
    content: "";
    position: absolute;
    top: -3px;
    left: -50px;
    width: 44px;
    height: 44px;
    background: url("../../assets/images/allergy/checking-mark-ok.svg");
    background-position: center center;
    background-size: contain;
  }
}
.allergy__check--false {
  color: $red;
  position: relative;
  &::before {
    content: "";
    position: absolute;
    top: -3px;
    right: -50px;
    width: 44px;
    height: 44px;
    background: url("../../assets/images/allergy/cheking-mark-not-ok.svg");
    background-position: center center;
    background-size: contain;
  }
}
.allergy__button__wrapper {
  margin: 0 0 35px;
}
.allergy-product {
  width: 800px;
  display: grid;
  grid-template-columns: 150fr 150fr 150fr 150fr 150fr;
  grid-template-rows: 130px 130px;
  gap: 10px 10px;
}
.allergy-product__item {
  background: $black;
  border: 1.5px solid $hover-btn-color;
  border-radius: 25px;
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  padding: 5px;
  position: relative;
  overflow: hidden;
  cursor: pointer;
  transition: $transition;

  &:hover {
    box-shadow: $shadow;
    transform: translateY(-5px);
  }
  & .allergy-product__false {
    position: absolute;
    background-color: rgba(68, 68, 68, 0.6);
    top: 0;
    left: 0;
    width: 102%;
    height: 102%;
  }
}
.allergy-product__item.allergy-product__item--false {
  border: 1.5px solid $red;
}
.allergy-product__item--img {
  margin: 0 0 15px;
}
.allergy-product__item--text {
  text-transform: uppercase;

  font-size: 1rem;
  line-height: 1.1rem;
}
.allergy-product__choice {
  position: absolute;
  top: 11px;
  right: 12px;
  z-index: 10;
}
.choice__true {
  width: 22px;
  height: 22px;
}
.choice__false {
  width: 22px;
  height: 22px;
}
.individual-products {
  max-width: 800px;
  margin: 0 auto;
  text-align: left;
}
.individual-products__text {
  color: $gold;
  margin: 0 0 10px 0;
}
.individual-products__wrapper-selector {
  width: 800px;
  margin: 10px 0 20px;
  display: flex;
  align-items: flex-start;
}
.individual-products__selector {
  width: 400px;
}
.products__selector {
  text-align: left;
  color: $black;
  background-color: $white;
  width: 330px;
  border-radius: 15px;
  padding: 10px 30px 10px 30px;
  font-size: 0.8889rem;
}

.multiselect__content-wrapper {
  position: absolute;
  margin: 20px 0 0;
  background-color: $white;
  border-radius: 15px;
  z-index: 1;
  width: 330px;
  left: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;
}
.multiselect__content {
  width: 100%;
}
.multiselect__select {
}
.multiselect__input {
  font-family: "Roboto", sans-serif;
  font-style: normal;
  font-weight: 300;
  font-size: 16px;
  line-height: 10px;
  width: 120px;
  &:active {
    border: 1px solid olivedrab;
  }
}
.multiselect__element {
}
.multiselect__option {
  display: block;
  text-align: center;
  padding: 10px 0;
  width: 100%;
  &:hover {
    background-color: $grey;
  }
}
.multiselect {
  height: 36px;
  position: relative;
}

.multiselect__tag {
  display: none;
}
.multiselect__content {
  align-items: center;
  width: 330px;
}
.individual-products__tag-wrap {
  width: 400px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  flex-wrap: wrap;
}
.individual-products__tag {
  font-family: "Roboto", sans-serif;
  font-style: normal;
  font-weight: 300;
  font-size: 13px;
  color: $black;
  background-color: $grey;
  border-radius: 10px;
  padding: 9px 9px 9px 9px;
  margin: 5px 0 0 0;
  position: relative;
  line-height: 10px;

  display: flex;
  align-items: center;

  & span + span {
    cursor: pointer;
    display: block;
    margin: 0 0 0 6px;
    padding: 3px;
    width: 10px;
    height: 10px;
    background: {
      image: url("./../../assets/images/allergy/cheking-mark-not-ok.svg");
      position: center center;
      size: cover;
      repeat: no-repeat;
    }
  }
}
.individual-products__tag + .individual-products__tag {
  margin: 5px 0 0 10px;
}

.allergy__button-next-wrapper {
  max-width: 800px;
  margin: 0 auto;
  display: flex;
  justify-content: flex-end;
}
</style>
