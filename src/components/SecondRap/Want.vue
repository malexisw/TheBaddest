<template>
  <div class="want-content">
    <div class="center d-flex" v-if="want">
      <div class="text un index2">
        <p class="what">what i</p>
        <p class="want">want</p>
      </div>
      <div class="text deux  index2">
        <p class="what">what i</p>
        <p class="want">want</p>
      </div>
      <div class="text trois index2">
        <p class="what">what i</p>
        <p class="want">want</p>
      </div>

      <div class="circle abs"></div>
    </div>

    <div class="clap d-flex w100 h100" v-if="clap">
      <div class="lines" v-for="item in 8" :key="item">
        <div class="clapSub d-flex gradDark">
          <p v-for="item in 8" :key="item">clap/clap//</p>
        </div>
        <div class="clapSub d-flex white">
          <p v-for="item in 8" :key="item">clap/clap//</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Want",
  data: () => ({
    want: true,
    clap: false,
  }),
  created() {
    setTimeout(() => (this.want = false), 800);

    setTimeout(() => (this.clap = true), 800);
  },
};
</script>

<style scoped>
.want-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  width: 100%;
  height: 100%;

  background: url(../../assets/bg/bg-second.jpg) center center/cover;

  animation: leaveRight 0.4s 2s forwards;
}

.center {
  justify-content: center;
  align-items: center;

  width: 80%;
  height: 70%;

  background: var(--first-bg);
  clip-path: inset(0 0 0 0);
}

.clap {
  flex-direction: column;
  justify-content: start;
  align-items: center;
}

.text {
  width: 25%;

  text-align: center;
}

.text p.what {
  font-size: 5em;
}

.text p.want {
  font-size: 8em;
  line-height: 80px;

  color: transparent;
  -webkit-text-stroke-width: 0.5px;
  -webkit-text-stroke-color: #fff;
}

.text.un p.what {
  animation: swapColorStroke 0.1s 0.2s forwards;
}
.text.un p.want {
  animation: swapColorWhite 0.1s 0.2s forwards;
}

.text.deux p.what {
  animation: swapColorStroke 0.1s 0.25s forwards;
}
.text.deux p.want {
  animation: swapColorWhite 0.1s 0.25s forwards;
}

.text.trois p.what {
  animation: swapColorStroke 0.1s 0.3s forwards;
}
.text.trois p.want {
  animation: swapColorWhite 0.1s 0.3s forwards;
}

.circle {
  border-radius: 50%;
  width: 500px;
  height: 500px;

  background: #221c4a;

  transform: scale(0);

  animation: circleAnime 0.5s 0.2s forwards;
}

.clap {
  background: var(--first-bg);
}

.clapSub p {
  font-size: 4em;
  line-height: 100px;
  margin-right: 5px;
}

.gradDark p {
  color: transparent;
  -webkit-text-stroke-width: 0.5px;
  -webkit-text-stroke-color: #fff;

  transform: translateX(-50%);

  animation: slideR 1.6s linear forwards;
}

.white p {
  transform: translateX(50%);
  animation: slideL 1.6s linear forwards;
}

@keyframes slideL {
  50% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-50%);
  }
}

@keyframes slideR {
  50% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(50%);
  }
}

@keyframes circleAnime {
  to {
    transform: scale(2);
  }
}

@keyframes swapColorStroke {
  to {
    color: transparent;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: #fff;
  }
}

@keyframes swapColorWhite {
  to {
    color: #fff;
  }
}

@keyframes leaveRight {
  to {
    transform: translateX(-100%);
  }
}

@media (max-width: 1100px) {
  .text {
    margin-right: 15px;
  }
}

@media (max-width: 400px) {
  .text p.what {
    font-size: 3em;
  }

  .text p.want {
    font-size: 6em;
    line-height: 60px;
  }
  .clapSub p {
    line-height: 60px;
  }
}
</style>
