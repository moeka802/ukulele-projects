<template>
  <div class="container">
    <h1 class="heroTitle">メジャースケールの運指</h1>
    <div class="fretboardContainer">
      <ukulele-fretboard :finger="1"></ukulele-fretboard>
      <ukulele-fretboard></ukulele-fretboard>
      <ukulele-fretboard :finger="3"></ukulele-fretboard>
      <ukulele-fretboard :finger="4" :isRootNote="true"></ukulele-fretboard>
      <ukulele-fretboard :finger="1"></ukulele-fretboard>
      <ukulele-fretboard :finger="2"></ukulele-fretboard>
      <ukulele-fretboard></ukulele-fretboard>
      <ukulele-fretboard :finger="4"></ukulele-fretboard>
      <ukulele-fretboard :finger="1" :isRootNote="true"></ukulele-fretboard>
      <ukulele-fretboard></ukulele-fretboard>
      <ukulele-fretboard :finger="3"></ukulele-fretboard>
      <ukulele-fretboard></ukulele-fretboard>
      <ukulele-fretboard></ukulele-fretboard>
      <ukulele-fretboard></ukulele-fretboard>
      <ukulele-fretboard></ukulele-fretboard>
      <ukulele-fretboard></ukulele-fretboard>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import UkuleleFretboard from "./components/UkuleleFretboard.vue";

export default defineComponent({
  name: "App",
  components: {
    UkuleleFretboard,
  },
});
</script>

<style>
body {
  margin: 0px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.container {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

h1.heroTitle {
  margin-bottom: 50px;
}

.fretboardContainer {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}
</style>
