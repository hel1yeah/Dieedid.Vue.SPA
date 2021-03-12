<template>
  <div class="calendar">
    <v-date-picker
      v-model="date"
      :header-color="red"
      event-color="#666"
      color='#222'
    ></v-date-picker>
    {{ date }}
  </div>
</template>

<script>
export default {
  name: "IndexCalendar",
  data() {
    return {
      date: null,
      red: "#555"
    };
  },
  methods: {}
};
</script>

<style lang="scss">
.red {
  color: red;
}
</style>
