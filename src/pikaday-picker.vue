<template>
  <input type="text" ref="input" :value="value" />
</template>

<script>
import Pikaday from "pikaday";
import "pikaday/css/pikaday.css";

export default {
  props: {
    value: {
      required: true
    },
    format: {
      default: "YYYY-MM-DD"
    },
    options: {
      default: () => ({})
    }
  },
  mounted: function() {
    const picker = new Pikaday({
      field: this.$refs.input,
      format: this.format,
      onSelect: () => {
        this.$emit("input", picker.toString());
      },
      ...this.options
    });
  }
};
</script>
