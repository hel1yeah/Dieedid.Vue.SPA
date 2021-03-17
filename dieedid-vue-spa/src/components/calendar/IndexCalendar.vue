<template>
  <div class="calendar" data-app>
    <v-menu
      :absolute="true"
      v-model="menu"
      :lose-on-click="true"
      :close-on-content-click="true"
      transition="scale-transition"
      min-width="290px"
      
      
    >
      <template v-slot:activator="{ on }">
        <v-text-field v-model="date" readonly v-on="on"></v-text-field>
      </template>

      <div class="test">
        <v-date-picker
          v-model="date"
          :header-color="grean"
          @input="menu = false"
        ></v-date-picker>
      </div>
    </v-menu>
  </div>
</template>

<script>
export default {
  name: "IndexCalendar",
  data() {
    return {
      // date: "2021-03-12",
      grean: "rgba(13, 168, 71, 1)",
      date: new Date().toISOString().substr(0, 10),
      menu: false,
      modal: false
    };
  }
};
</script>

<style lang="scss">
.calendar {
}
.v-menu__content .theme--light .menuable__content__active {
  top: 0;
  right: -305px;
}
// .v-picker v-card.v-picker--date.theme--light {
//   top: 0px;
//   right: -305px;
// }
</style>
