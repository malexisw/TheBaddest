<template>
  <div class="d-flex content">
    <div class="backFirst abs"></div>
    <div class="backSecond index1">
      <p class="gradStroke top1">dead</p>
      <p class="gradStroke top2 index1">dead</p>
      <p class="dead index3">dead</p>
      <p class="gradStroke bot2 index1">dead</p>
      <p class="gradStroke bot1">dead</p>
    </div>
    <div class="backthird index3 abs" v-if="visible"></div>
  </div>
</template>

<script>
export default {
  name: "Skull",
  data: () => ({
    visible: false,
  }),
  created() {
    setTimeout(() => (this.visible = true), 1650);
  },
};
</script>

<style scoped>
.content {
  justify-content: center;
  align-items: center;

  width: 100%;
  height: 100%;

  background: transparent;
}

.backFirst {
  height: 0%;
  width: 0%;

  background: var(--first-bg);

  animation: backgroundFirstSet 0.6s linear forwards;
}

.backSecond {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  height: 0%;
  width: 0%;

  background: var(--first-bg);

  animation: backgroundSecondSet 0.6s 0.3s linear forwards;
}

.backthird {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  height: 100%;
  width: 100%;

  background: #21345f;

  animation: bgThird 0.6s 0.15s forwards;
}

p {
  font-size: 16em;
  font-weight: bold;

  line-height: 300px;
}

p.dead {
  color: transparent;
  background: url("../../assets/bg/bg-second.jpg") center center/cover no-repeat;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;

  visibility: hidden;
  letter-spacing: 200px;
  transform: scale(2);

  animation: transformReset 0.4s 0.85s forwards;
}

.top1 {
  background: -webkit-linear-gradient(
    top,
    #93bbec 0%,
    #c3a8f9 60%,
    transparent 60%
  );
  -webkit-background-clip: text;
  -webkit-text-stroke: 2px transparent;

  transform: translateY(140%);
  visibility: hidden;

  animation: appearT1 0.6s 1.3s forwards;
}

.top2 {
  background: -webkit-linear-gradient(
    top,
    #93bbec 0%,
    #c3a8f9 65%,
    transparent 65%
  );
  -webkit-background-clip: text;
  -webkit-text-stroke: 2px transparent;

  transform: translateY(120%);
  visibility: hidden;

  animation: appearT2 0.55s 1.2s forwards;
}

.bot1 {
  background: -webkit-linear-gradient(
    top,
    transparent 35%,
    #c3a8f9 35%,
    #93bbec 100%
  );
  -webkit-background-clip: text;
  -webkit-text-stroke: 2px transparent;

  transform: translateY(-140%);
  visibility: hidden;

  animation: appearB1 0.5s 1.25s forwards;
}

.bot2 {
  background: -webkit-linear-gradient(
    top,
    transparent 40%,
    #c3a8f9 40%,
    #93bbec 100%
  );
  -webkit-background-clip: text;
  -webkit-text-stroke: 2px transparent;

  transform: translateY(-120%);
  visibility: hidden;

  animation: appearB2 0.4s 1.15s forwards;
}

@keyframes bgThird {
  0% {
    background: var(--first-bg);
  }
  100% {
    background: var(--first-bg);
    transform: translateX(-100%);
  }
}

@keyframes appearT2 {
  0% {
    visibility: visible;
  }
  20% {
    visibility: visible;
    transform: translateY(40%);
  }
  97% {
    visibility: hidden;
    transform: translateY(40%);
  }
  100% {
    visibility: hidden;
    transform: translateY(40%);
  }
}

@keyframes appearT1 {
  0% {
    visibility: visible;
  }
  20% {
    visibility: visible;
    transform: translateY(85%);
  }
  95% {
    visibility: hidden;
    transform: translateY(85%);
  }
  100% {
    visibility: hidden;
    transform: translateY(85%);
  }
}

@keyframes appearB2 {
  0% {
    visibility: visible;
  }
  20% {
    visibility: visible;
    transform: translateY(-40%);
  }
  95% {
    visibility: hidden;
    transform: translateY(-40%);
  }
  100% {
    visibility: hidden;
    transform: translateY(-40%);
  }
}

@keyframes appearB1 {
  0% {
    visibility: visible;
  }
  20% {
    visibility: visible;
    transform: translateY(-80%);
  }
  97% {
    visibility: hidden;
    transform: translateY(-80%);
  }
  100% {
    visibility: hidden;
    transform: translateY(-80%);
  }
}

@keyframes transformReset {
  0% {
    visibility: visible;
  }
  100% {
    visibility: visible;
    letter-spacing: 10px;
    transform: scale(1);
  }
}

@keyframes backgroundSecondSet {
  0% {
    border: 5px solid #8363f2;
  }
  100% {
    border: 1px solid #8363f2;
    height: 100%;
    width: 100%;
  }
}

@keyframes backgroundFirstSet {
  0% {
    border: 1px solid #c9c8d0;
  }
  100% {
    border: 1px solid #c9c8d0;
    height: 100%;
    width: 100%;
  }
}
</style>
