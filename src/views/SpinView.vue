<template>
  <div class="body">
    <button @click="startSpin" id="spin">Spin</button>
    <span class="arrow"></span>
    <div ref="containerSpin" class="container">
      <div  :class="'spin_' + i" v-for="(name, i) in nameArray" :key="i" class="one">Đoàn</div>
      <div class="one">Đoàn</div>
      <div class="two">2</div>
      <div class="three">3</div>
      <div class="four">4</div>
      <div class="five">5</div>
      <div class="six">6</div>
      <div class="seven">7</div>
      <div class="eight">8a</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number: this.getRandomNumber(),
      nameArray: ["Doan", "Doan"],
    };
  },
  methods: {
    startSpin() {
      this.$refs.containerSpin.style.transform = "rotate(" + this.number + "deg)";
      this.number += this.getRandomNumber();
    },
    getRandomNumber() {
      return Math.ceil(Math.random() * 3000) + 1000;
    },
    // styleObject: {
    //   color: 'red',
    //   fontSize: '13px'
    // }
  },
};
</script>

<style scoped>
.body {
  margin: 0;
  padding: 0;
  background-color: #34495e;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  overflow: hidden;
  position: relative;
}

.container {
  width: 500px;
  height: 500px;
  background-color: #ccc;
  border-radius: 50%;
  border: 15px solid #dde;
  position: relative;
  overflow: hidden;
  transition: 5s;
}

.container div {
  height: 50%;
  width: 200px;
  position: absolute;
  clip-path: polygon(100% 0, 50% 100%, 0 0);
  transform: translateX(-50%);
  transform-origin: bottom;
  display: flex;
  align-items: center;
  justify-content: start;
  font-size: 20px;
  font-weight: bold;
  font-family: sans-serif;
  color: #fff;
  left: 135px;
  writing-mode: vertical-rl;
  text-orientation: mixed;
  padding-top: 6px;
}

.container .one {
  background-color: #3f51b5;
  left: 50%;
}
.container .two {
  background-color: #ff9800;
  transform: rotate(45deg);
}
.container .three {
  background-color: #e91e63;
  transform: rotate(90deg);
}
.container .four {
  background-color: #4caf50;
  transform: rotate(135deg);
}
.container .five {
  background-color: #009688;
  transform: rotate(180deg);
}
.container .six {
  background-color: #795548;
  transform: rotate(225deg);
}
.container .seven {
  background-color: #9c27b0;
  transform: rotate(270deg);
}
.container .eight {
  background-color: #f44336;
  transform: rotate(315deg);
}

.arrow {
  position: absolute;
  top: 10%;
  left: 50%;
  transform: translateX(-50%);
  color: #140a24;
  z-index: 1;
}

.arrow::before {
  content: "\1F817";
  font-size: 70px;
}

#spin {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 10;
  background-color: #e2e2e2;
  text-transform: uppercase;
  border: 8px solid #fff;
  font-weight: bold;
  font-size: 20px;
  color: #a2a2a2;
  width: 80px;
  height: 80px;
  font-family: sans-serif;
  border-radius: 50%;
  cursor: pointer;
  outline: none;
  letter-spacing: 1px;
}
</style>
