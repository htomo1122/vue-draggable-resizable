<template>
  <div id="app">
    <div
      :style="`height: ${height}px; width: ${width}px; border: 1px solid red; position: relative;`"
    >
      <vue-draggable-resizable
        :w="200"
        :h="200"
        :parent="true"
        :min-width="200"
        :min-height="200"
      >
        <p>vue-draggable-resizable</p>
      </vue-draggable-resizable>
    </div>
    <button @click="width += 50">Increase width</button>
    <button @click="width -= 50">Decrease width</button>

    <button @click="height += 50">Increase height</button>
    <button @click="height -= 50">Decrease height</button>

    <button @click="()=>{ width = 500; height = 500;}">Reset</button>
  </div>
</template>

<script>
import VueDraggableResizable from "./components/vue-draggable-resizable.vue";
import "./components/vue-draggable-resizable.css";

export default {
  name: "app",
  components: {
    VueDraggableResizable,
  },
  data() {
    return {
      width: 500,
      height: 500,
    };
  },
};
</script>

<style>
.vdr {
  border: 1px dashed black;
}
</style>
