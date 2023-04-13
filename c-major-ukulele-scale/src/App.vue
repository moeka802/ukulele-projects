<template>
  <div class="container">
    <h1 class="heroTitle">C Major Ukulele Scale</h1>
    <div class="fretboardContainer">
      <fret v-for="(note, i) in notes" :key="i" :note="note"></fret>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Fret from "./components/FretComponent.vue";
const NOTES = [
  { name: "A" },
  { name: "B♭" },
  { name: "B" },
  { name: "C" },
  { name: "D♭" },
  { name: "D" },
  { name: "E♭" },
  { name: "E" },
  { name: "F" },
  { name: "G♭" },
  { name: "G" },
  { name: "A♭" },
  { name: "A" },
  { name: "B♭" },
  { name: "B" },

  { name: "E" },
  { name: "F" },
  { name: "G♭" },
  { name: "G" },
  { name: "A♭" },
  { name: "A" },
  { name: "B♭" },
  { name: "B" },
  { name: "C" },
  { name: "D♭" },
  { name: "D" },
  { name: "E♭" },
  { name: "E" },
  { name: "F" },
  { name: "G♭" },

  { name: "C" },
  { name: "D♭" },
  { name: "D" },
  { name: "E♭" },
  { name: "E" },
  { name: "F" },
  { name: "G♭" },
  { name: "G" },
  { name: "A♭" },
  { name: "A" },
  { name: "B♭" },
  { name: "B" },
  { name: "C" },
  { name: "D♭" },
  { name: "D" },

  { name: "G" },
  { name: "A♭" },
  { name: "A" },
  { name: "B♭" },
  { name: "B" },
  { name: "C" },
  { name: "D♭" },
  { name: "D" },
  { name: "E♭" },
  { name: "E" },
  { name: "F" },
  { name: "G♭" },
  { name: "G" },
  { name: "A♭" },
  { name: "A" },
];

export default defineComponent({
  name: "App",
  components: {
    Fret,
  },
  data() {
    return {
      isReady: false,
      notes: [] as any,
    };
  },
  mounted() {
    this.notes = NOTES.map((note) => {
      if (["C", "D", "E", "F", "G", "A", "B"].includes(note.name)) {
        return {
          ...note,
          isVisible: true,
          isRoot: note.name === "C",
        };
      } else {
        return {
          name: "",
          isVisible: false,
          isRoot: false,
        };
      }
    });
  },
});
</script>

<style>
body {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
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

h1 {
  margin-bottom: 50px;
}

.fretboardContainer {
  display: grid;
  grid-template-columns: repeat(15, 1fr);
}
</style>
