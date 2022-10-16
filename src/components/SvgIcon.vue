<template>
  <svg :class="svgClass" aria-hidden="true">
    <use :xlink:href="iconName" />
  </svg>
</template>

<script setup>
import { defineProps, computed } from "vue";

const props = defineProps({
  iconClass: {
    type: String,
    required: true,
  },
  className: {
    type: String,
    default: "",
  },
});

const iconName = computed(() => `#icon-${props.iconClass}`);
const svgClass = computed(() => {
  if (props.className) {
    return "svg-icon " + props.className;
  } else {
    return "svg-icon";
  }
});
</script>

<style scoped>
.svg-icon {
  width: 3em;
  height: 3em;
  vertical-align: -0.15em;
  fill: currentColor;
  overflow: hidden;
}
</style>
