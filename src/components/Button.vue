<template>
  <button :class="ui.cls">
    <slot></slot>
  </button>
</template>

<script>
import { reactive, ref } from "vue";
export default {
  props: {
    color: {
      type: String,
      default: "blue",
    },
  },
  setup(props) {
    const ui = reactive({
      cls: ref(`py-2 px-4 rounded text-white bg-${props.color}-500 hover:bg-${props.color}-700`),
    });
    return {
      ui,
    };
  },
};
</script>