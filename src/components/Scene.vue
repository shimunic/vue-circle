<template>
  <div id="scene">
    <img 
    src="../assets/smiley-round.png" 
    :style="{
      marginTop: marginTopNum + 'px',
      marginBottom: marginBottomNum + 'px',
      marginLeft: marginLeftNum + 'px',
      marginRight: marginRightNum + 'px',
      }" 
    />
  </div>
</template>

<script>
import { eventBus } from '../main';

export default {
  name: 'Scene',
  num: 0,
  data() {
    return {
      marginTopNum: 0,
      marginBottomNum: 0,
      marginLeftNum: 0,
      marginRightNum: 0,
    };
  },
  created() {
    eventBus.$on('up', clicked => {
      if (clicked) {
        this.marginBottomNum += 50;
      }
    });
    eventBus.$on('down', clicked => {
      if (clicked) {
        this.marginTopNum += 50;
      }
    });
    eventBus.$on('left', clicked => {
      if (clicked) {
        this.marginLeftNum -= 50;
      }
    });
    eventBus.$on('right', clicked => {
      if (clicked) {
        this.marginRightNum -= 50;
      }
    });
  },
};
</script>

<style scoped>
#scene {
  width: 50%;
  height: 700px;
  border: 1px solid black;
  background-color: lightyellow;
  display: flex;
  justify-content: center;
  align-items: center;
}
img {
  width: 200px;
  height: 200px;
}
#bbb {

}
</style>