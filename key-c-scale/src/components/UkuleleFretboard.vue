<template>
  <div class="fret">
    <div v-if="fingerName" class="fretFinger">{{ fingerName }}</div>
  </div>
</template>

<script lang="ts">
const fingerNames = ["親", "人", "中", "薬", "小"];
export default {
  props: {
    finger: {
      type: Number,
    },
    isRootNote: {
      type: Boolean,
    },
  },
  computed: {
    fingerName() {
      if (!this.finger) return;
      return fingerNames[this.finger];
    },
    theme() {
      return this.isRootNote
        ? { color: "#fff", backgroundColor: "#ff7f50", borderColor: "#ff524f" }
        : { color: "#000", backgroundColor: "#fff", borderColor: "#000" };
    },
  },
};
</script>

<style>
.fret {
  position: relative;
  width: 60px;
  height: 60px;
  border-top: 1px solid #000;
  border-left: 1px solid #000;
  z-index: 1;
}
.fretFinger {
  position: absolute;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;

  color: v-bind("theme.color");
  background-color: v-bind("theme.backgroundColor");

  border: 1px solid v-bind("theme.borderColor");
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.fret:nth-of-type(n + 13) {
  border-left: 0px;
}
</style>
