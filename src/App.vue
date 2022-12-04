<script>
import axios from 'axios';
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
      id: 2018,
      advice: "Love you 3000"
    }
  },
  methods: {
    getNewAdvice() {
      axios
        .get('https://api.adviceslip.com/advice')
        .then(res => {
          this.id = res.data.slip.id;
          this.advice = res.data.slip.advice;
      });
    },
    clickDice() {
      this.getNewAdvice();
    }
  },
  mounted () {
    this.getNewAdvice();
  },
}
</script>

<template>
  <AdviceCard :id="id" :advice="advice" />
  <DiceButton @click-dice="clickDice" />
</template>

<style scoped>

</style>