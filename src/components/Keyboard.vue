<template>
  <div id="keyboard">
    <button :disabled="buttonDisabled" class="up" @click="moveUp()">↑</button>
    <br />
    <button class="left" @click="moveLeft()">←</button>
    <button class="down" @click="moveDown()">↓</button>
    <button class="right" @click="moveRight()">→</button>
  </div>
</template>

<script>
import { eventBus } from '../main';
export default {
  data() {
    return {
      clicked: false,
      upButtonLimit: 10,
      buttonDisabled: false,
    };
  },
  methods: {
    moveUp() {
      this.clicked = true;
      eventBus.$emit('up', this.clicked);
      this.clicked = false;
      this.upButtonLimit -= 1;
    },
    moveDown() {
      this.clicked = true;
      eventBus.$emit('down', this.clicked);
      this.clicked = false;
    },
    moveLeft() {
      this.clicked = true;
      eventBus.$emit('left', this.clicked);
      this.clicked = false;
    },
    moveRight() {
      this.clicked = true;
      eventBus.$emit('right', this.clicked);
      this.clicked = false;
    },
  
  },
  updated() {
    if (this.upButtonLimit === 0) {
      this.buttonDisabled = true;
    }
  }
};
</script>

<style scoped>
#keyboard {
  width: 50%;
  height: 700px;
  border: 1px solid black;
  background-color: rgb(181, 237, 181);
  /* display: flex; */
  justify-content: center;
  align-items: center;
}
button {
  width: 100px;
  height: 100px;
  font-size: 30px;
}
.up {
  margin-left: 100px;
}
</style>