<script>
import Vue from "vue";
import PikadayPicker from "@/pikaday-picker.vue";

export default Vue.extend({
  name: "ServeDev",
  components: {
    PikadayPicker
  },
  data() {
    return {
      defaultDate: "19/11/1990",
      date: ""
    };
  }
});
</script>

<template>
  <div id="app">
    <pikaday-picker
      v-model="date"
      value="19/11/1990"
      format="DD/MM/YYYY"
      :options="{ firstDay: 3 }"
    />
  </div>
</template>
