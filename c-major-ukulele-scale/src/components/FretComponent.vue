<template>
  <div class="fret">
    <div v-if="note.isVisible" class="fretFinger">{{ note.name }}</div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    note: {
      type: Object,
    },
  },
  computed: {
    theme() {
      return this.note.isRoot
        ? { color: "#fff", backgroundColor: "#ff7f50" }
        : { color: "#999", backgroundColor: "#eee" };
    },
  },
});
</script>

<style>
.fret {
  position: relative;
  width: 60px;
  height: 60px;
  border-top: 1px solid #2c3e50;
  border-left: 1px solid #2c3e50;
  z-index: 10;
}

.fretFinger {
  position: absolute;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 20;

  background: v-bind("theme.backgroundColor");
  color: v-bind("theme.color");
  font-weight: bold;

  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.fret:nth-of-type(15n + 1) {
  border-left: 0px;
}
.fret:nth-of-type(15n + 2) {
  border-left-style: dotted;
}
.fret:nth-of-type(n + 46) {
  border-left: 0px;
}
</style>
