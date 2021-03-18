<template>
  <div class="calendar">
    <div class="activity--button calendar__age" @click="menu = !menu">
      <svg class="calendar__icon">
        <use xlink:href="@/assets/images/sprite/sprite.svg#calendar"></use>
      </svg>

      <div class="calendar__text-field">{{ date }}</div>
    </div>

    <div class="date-picker__position">
      <v-date-picker
        v-if="menu"
        v-model="date"
        :color="grean"
        :scrollable="true"
        width="250"
      ></v-date-picker>
    </div>
  </div>
</template>

<script>
export default {
  name: "IndexCalendar",
  data() {
    return {
      grean: "rgba(13, 168, 71, 1)",
      date: new Date().toISOString().substr(0, 10),
      menu: false,
      modal: false
    };
  },
  methods: {
    test() {}
  }
};
</script>

<style lang="scss">
.calendar {
  position: relative;

  &__icon {
    width: 32px;
    height: 32px;
    margin: 0 40px 0 0;
    fill: $hover-btn-color;
    transition: 0.2s;
    &:hover {
      fill: $white;
    }
  }
  &__age {
    display: flex;
    color: $hover-btn-color;
    &:hover .calendar__icon {
      fill: $white;
    }
  }
}
.date-picker__position {
  position: absolute;
  top: 0;
  right: -270px;
  z-index: 55;
}
.v-picker.v-card.v-picker--date.theme--light {
  border-radius: 10px;
}
.v-date-picker-table.v-date-picker-table--date.theme--light {
  height: 200px;
}
</style>
