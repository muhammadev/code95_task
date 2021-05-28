<template>
  <div id="app">
    <top-bar />
    <nav-bar />
    <keep-alive>
      <component :is="currentStep" v-on:step="switchStep"></component>
    </keep-alive>
  </div>
</template>

<script>
import TopBar from "./components/TopBar";
import NavBar from "./components/NavBar";
import StepOne from "./components/StepOne.vue";
import StepTwo from "./components/StepTwo.vue";

export default {
  name: "App",
  data() {
    return {
      currentStep: StepOne,
    };
  },
  methods: {
    switchStep: function(event) {
      // console.log("switching now..", event)
      this.currentStep = event === 0 ? StepOne : StepTwo;
    }
  },
  components: {
    TopBar,
    NavBar,
    StepOne,
    StepTwo,
  },
};
</script>

<style lang="scss">
@font-face {
  font-family: DINNextMeduim;
  src: url("./assets/DINNextLTArabic-Medium-2.ttf");
}

* {
  margin: 0;
  padding: 0;
}

#app {
  font-family: DINNextMeduim, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>