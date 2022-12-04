<script>
import PatternDividerDesktop from './icons/PatternDividerDesktop.vue';
import PatternDividerMobile from './icons/PatternDividerMobile.vue';

export default {
  name: 'AdviceCard',
  props: {
    id: Number,
    advice: String,
  },
  components: {
    PatternDividerDesktop,
    PatternDividerMobile
  },
  data() {
    return {
      screenWidth: 0,
    };
  },
  mounted() {
    this.updateScreenWidth();
    this.onScreenResize();
  },
  methods: {
    onScreenResize() {
      window.addEventListener("resize", () => {
        this.updateScreenWidth();
      });
    },
    updateScreenWidth() {
      this.screenWidth = window.innerWidth;
    },
  }
}
</script>

<template>
  <div id="card">
    <h1 class="mb1">Advice #{{ id }}</h1>
    <p class="mb2">"{{ advice }}"</p>
    <PatternDividerDesktop v-show="this.screenWidth >= 768" id="divider-desktop"/>
    <PatternDividerMobile v-show="this.screenWidth < 768" id="divider-mobile" />
  </div>
</template>

<style>
#card {
  background-color: hsl(217, 19%, 24%);
  padding: 4rem;
  border-radius: 1rem;
  text-align: center;
  align-items: center;
  justify-content: center;
}
@media (max-width: 768px) {
  #card {
    padding: 2rem 1.5rem 3.5rem;
    width: 331px;
  }
}
@media (min-width: 769px) {
  #card {
    width: 540px;
  }
}
</style>