<template>
  <div class="fire h100">
    <div class="text">
      <div class="world d-flex">
        <p class="gradStroke left">w</p>
        <p id="mid" class="gradStroke">world</p>
        <p class="gradStroke right">d</p>
      </div>
      <p class="on gradStroke" v-if="on">on</p>
      <p class="grad fText" v-if="fire">fire</p>
    </div>
    <div class="bgSlide abs h100 w100">
      <div class="top"></div>
      <div class="middle"></div>
      <div class="bottom"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Fire",
  data: () => ({
    on: false,
    fire: false,
  }),
  created() {
    setTimeout(() => (this.on = true), 300);
    setTimeout(() => (this.fire = true), 800);
  },
};
</script>

<style scoped>
.fire,
.text {
  display: flex;
  justify-content: center;
  align-items: center;

  width: 100%;
}

.text {
  animation: slideTextLeft 0.3s 1.3s forwards;
}

.world {
  align-items: center;
  justify-content: center;

  position: relative;

  width: 80%;
  animation: widthChange 0.1s 0.3s forwards;
  margin-right: 25px;
}

#mid {
  text-align: center;
  width: 97%;
}

#mid::before {
  width: 40%;
  content: " ";
  position: absolute;
  background: var(--first-bg);
  left: 0px;
  bottom: 50%;
  transform: translateY(49%);
  height: 112px;

  background-position: 0 0, 0 100%;
  background-repeat: no-repeat;
  -webkit-background-size: 100% 1px;
  -moz-background-size: 100% 1px;
  background-size: 100% 1px;
  background-image: -webkit-linear-gradient(
      top,
      #93bbec 0%,
      #c3a8f9 50%,
      #93bbec 100%
    ),
    -webkit-linear-gradient(top, #93bbec 0%, #c3a8f9 50%, #93bbec 100%);
  background-image: -moz-linear-gradient(
      top,
      #93bbec 0%,
      #c3a8f9 50%,
      #93bbec 100%
    ),
    -moz-linear-gradient(top, #93bbec 0%, #c3a8f9 50%, #93bbec 100%);
  background-image: -o-linear-gradient(
      top,
      #93bbec 0%,
      #c3a8f9 50%,
      #93bbec 100%
    ),
    -o-linear-gradient(top, #93bbec 0%, #c3a8f9 50%, #93bbec 100%);
  background-image: linear-gradient(
      to top,
      #93bbec 0%,
      #c3a8f9 50%,
      #93bbec 100%
    ),
    linear-gradient(to top, #93bbec 0%, #c3a8f9 50%, #93bbec 100%);

  z-index: 1;

  animation: goRightBefore 0.3s forwards;
}

.left {
  position: absolute;
  left: 0;

  animation: goRight 0.3s forwards;
}

#mid::after {
  width: 40.5%;
  content: " ";
  position: absolute;
  background: var(--first-bg);
  right: 0;
  bottom: 50%;
  transform: translateY(49%);
  height: 112px;

  background-position: 0 0, 0 100%;
  background-repeat: no-repeat;
  -webkit-background-size: 100% 1px;
  -moz-background-size: 100% 1px;
  background-size: 100% 1px;
  background-image: -webkit-linear-gradient(
      top,
      #93bbec 0%,
      #c3a8f9 50%,
      #93bbec 100%
    ),
    -webkit-linear-gradient(top, #93bbec 0%, #c3a8f9 50%, #93bbec 100%);
  background-image: -moz-linear-gradient(
      top,
      #93bbec 0%,
      #c3a8f9 50%,
      #93bbec 100%
    ),
    -moz-linear-gradient(top, #93bbec 0%, #c3a8f9 50%, #93bbec 100%);
  background-image: -o-linear-gradient(
      top,
      #93bbec 0%,
      #c3a8f9 50%,
      #93bbec 100%
    ),
    -o-linear-gradient(top, #93bbec 0%, #c3a8f9 50%, #93bbec 100%);
  background-image: linear-gradient(
      to top,
      #93bbec 0%,
      #c3a8f9 50%,
      #93bbec 100%
    ),
    linear-gradient(to top, #93bbec 0%, #c3a8f9 50%, #93bbec 100%);

  z-index: 1;

  animation: goLeftAfter 0.3s forwards;
}

.right {
  position: absolute;
  right: 0;

  animation: goLeft 0.3s forwards;
}

.on {
  margin-right: 25px;

  position: relative;

  animation: slideLeft 0.6s forwards;
}

.fText {
  transform: scale(2.5);

  animation: scaleDown 0.4s forwards;
}

.bgSlide {
  display: flex;
  flex-direction: column;

  animation: slideLeftAll 0.25s 1.5s forwards;
}

.top,
.middle,
.bottom {
  position: absolute;
  left: 100%;

  height: 33%;
  width: 70%;
}

.top {
  background: url("../../assets/bg/bg-second.jpg") top/cover no-repeat;

  animation: slideBgLeft 0.2s 1.3s forwards;
}

.middle {
  top: 33%;
  background: url("../../assets/bg/bg-second.jpg") center/cover no-repeat;
  animation: slideBgLeft 0.2s 1.25s forwards;
}

.bottom {
  top: 66%;
  height: 34%;
  background: url("../../assets/bg/bg-second.jpg") bottom/cover no-repeat;
  animation: slideBgLeft 0.2s 1.3s forwards;
}

@keyframes slideLeftAll {
  to {
    transform: translateX(-70%);
  }
}

@keyframes slideBgLeft {
  to {
    left: 0;
  }
}

@keyframes slideTextLeft {
  to {
    transform: translateX(-100%);
  }
}

@keyframes scaleDown {
  to {
    visibility: visible;
    transform: scale(1);
  }
}

@keyframes slideLeft {
  to {
    left: 0;
  }
}

@keyframes widthChange {
  to {
    width: 350px;
  }
}

@keyframes goRightBefore {
  to {
    left: 40%;
    width: 0px;
  }
}

@keyframes goRight {
  to {
    left: 39%;
    opacity: 0;
  }
}

@keyframes goLeftAfter {
  to {
    right: 40%;
    width: 0px;
  }
}

@keyframes goLeft {
  to {
    right: 39%;
    opacity: 0;
  }
}

@media (max-width: 800px) {
  @keyframes widthChange {
    to {
      width: 250px;
    }
  }
}

@media (max-width: 400px) {
  @keyframes widthChange {
    to {
      width: 150px;
    }
  }
}
</style>
