<script>
import DiceIcon from './icons/DiceIcon.vue';

export default {
  name: 'DiceButton',
  components: {
    DiceIcon
  }
}
</script>

<template>
  <button @click="$emit('click-dice')">
    <DiceIcon />
  </button>
</template>