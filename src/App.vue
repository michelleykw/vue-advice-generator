<script>
import AdviceCard from './components/AdviceCard.vue';
import DiceButton from './components/DiceButton.vue';

export default {
  name: 'App',
  components: {
    AdviceCard,
    DiceButton,
  },
  data() {
    return {
      advice: "Love you 3000"
    }
  },
  methods: {
    clickDice() {
      console.log('Roll dice');
      this.advice = "I miss you"
    }
  }
}
</script>

<template>
  <AdviceCard :advice="advice"/>
  <DiceButton @click-dice="clickDice" />
</template>

<style scoped>

</style>
