<template>
  <div>
    <span class="progress-bar-seconds">{{ seconds }} Seconds left ...</span>
  </div>
</template>

<script>
import { ref, onMounted, onUnmounted } from "vue";

export default {
  props: {
    value: {
      type: Number,
      default: 0,
      required: true,
    },
  },
  setup(props) {
    const seconds = ref(0);
    let _timerId = null;

    onMounted(() => {
      seconds.value = props.value;
      if (seconds.value > 0) {
        _timerId = setInterval(() => {
          seconds.value--;
          if (seconds.value <= 0) {
            clearInterval(_timerId);
          }
        }, 1000);
      }
    });

    onUnmounted(() => clearInterval(_timerId));

    return {
      seconds,
    };
  },
};
</script>