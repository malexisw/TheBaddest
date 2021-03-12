<template>
  <div class="live">
    <p class="text abs index1" v-if="this.text">live</p>

    <div class="square abs" v-if="this.square"></div>

    <div class="wild" v-if="this.wild">
      <p>
        <span class="R">r</span><span class="E">e</span><span class="A">a</span
        ><span class="L1">l</span>
      </p>
      <p>
        <span class="W">w</span><span class="I">i</span><span class="L2">l</span
        ><span class="D">d</span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Live",
  data: () => ({
    text: true,
    square: false,
    wild: false,
  }),
  created() {
    setTimeout(() => (this.text = false), 700);
    setTimeout(() => (this.square = true), 700);
    setTimeout(() => (this.wild = true), 750);
  },
};
</script>

<style scoped>
.live {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;

  animation: flash 0.2s 0.4s 1;
}

.text {
  transform: scale(11, 5);
  animation: liveText 0.7s forwards;
}

.square {
  background: -webkit-linear-gradient(top, #93bbec, #c3a8f9, #93bbec);
  width: 25%;
  height: 30%;

  right: 10%;
  top: 25%;

  animation: squareAnim 1.3s forwards;
}

.wild {
  transform: scale(15, 3);
  animation: scaleDown 0.5s forwards;
}

.E {
  animation: colored 1.5s 0.3s forwards;
}

.A {
  animation: colored 1.45s 0.35s forwards;
}

.I {
  animation: colored 1.4s 0.4s forwards;
}

.W {
  animation: colored 1.35s 0.45s forwards;
}

.L2 {
  animation: colored 1.3s 0.5s forwards;
}

.L1 {
  animation: colored 1.25s 0.55s forwards;
}

.R {
  animation: colored 1.2s 0.6s forwards;
}

.D {
  animation: colored 1.15s 0.65s forwards;
}

span {
  color: transparent;
  -webkit-text-stroke-width: 0.5px;
  -webkit-text-stroke-color: #93bbec;
}

p {
  letter-spacing: 20px;

  animation: letterspace 0.7s forwards;
}

@keyframes flash {
  50% {
    background: #8b97c7;
  }
  100% {
    background: transparent;
  }
}

@keyframes colored {
  1% {
    background: -webkit-linear-gradient(#93bbec, #c3a8f9, #93bbec);
    -webkit-background-clip: text;
    -webkit-text-stroke: 2px transparent;
  }
  50% {
    background: -webkit-linear-gradient(#93bbec, #c3a8f9, #93bbec);
    -webkit-background-clip: text;
    -webkit-text-stroke: 2px transparent;
  }
  100% {
    background: transparent;
    -webkit-background-clip: text;
    -webkit-text-stroke: 2px transparent;
  }
}

@keyframes letterspace {
  to {
    letter-spacing: 0;
  }
}

@keyframes scaleDown {
  to {
    transform: scale(2, 2);
  }
}

@keyframes squareAnim {
  10% {
    right: 8%;

    height: 35%;
  }
  35% {
    right: 30%;
    height: 35%;
  }
  60% {
    right: 30%;
    height: 5%;
  }
  75% {
    right: 30%;
    height: 5%;
  }
  100% {
    height: 5%;
    right: 110%;
  }
}

@keyframes liveText {
  15% {
    color: transparent;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: white;

    transform: scale(11, 2);
  }
  25% {
    color: transparent;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: white;

    transform: scale(11, 2);
  }
  40% {
    color: transparent;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: white;

    transform: scale(11, 2);
  }
  60% {
    color: transparent;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: white;

    transform: scale(5, 2);
  }
  100% {
    color: #fff;

    transform: scale(2, 2);
  }
}

@media (max-width: 800px) {
  .square {
    top: 30%;
  }
}

@media (max-width: 400px) {
  .square {
    top: 35%;
  }
}
</style>
