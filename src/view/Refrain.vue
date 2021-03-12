<template>
  <div class="refrain">
    <!-- Text component -->
    <div class="abs d-flex" v-if="coming">
      <Coming />
    </div>

    <div class="abs d-flex w100 h100" v-if="live">
      <Live />
    </div>

    <div class="abs d-flex" v-if="light">
      <Light />
    </div>

    <div class="abs d-flex w100 h100" v-if="fire">
      <Fire />
    </div>

    <div class="abs d-flex w100 h100" v-if="casser">
      <Break />
    </div>

    <div class="abs d-flex w100 h100 slideUpLeave" v-if="card">
      <Card />
      <div class="square abs"></div>
    </div>

    <div class="abs d-flex w100 h100 slideLeftLeave" v-if="visual">
      <Visual />
    </div>

    <div class="abs d-flex w100 h100" v-if="never">
      <Never />
    </div>

    <div class="abs d-flex w100 h100 slideRightArrive" v-if="diamSplash">
      <DiamSplash />
    </div>

    <div class="abs d-flex w100 h100" v-if="end">
      <End />
    </div>
  </div>
</template>

<script>
import Coming from "../components/Refrain/Coming.vue";
import Live from "../components/Refrain/Live.vue";
import Light from "../components/Refrain/Light.vue";
import Fire from "../components/Refrain/Fire.vue";
import Break from "../components/Refrain/Break.vue";
import Card from "../components/Refrain/card.vue";
import Visual from "../components/Refrain/Visual";
import Never from "../components/Refrain/Never.vue";
import DiamSplash from "../components/Refrain/DiamSplash.vue";
import End from "../components/Refrain/End.vue";

export default {
  name: "Refrain",
  components: {
    Coming,
    Live,
    Light,
    Fire,
    Break,
    Card,
    Visual,
    Never,
    DiamSplash,
    End,
  },
  data: () => ({
    coming: true,
    live: false,
    light: false,
    fire: false,
    casser: false,
    card: false,
    visual: false,
    never: false,
    diamSplash: false,
    end: false,
  }),
  created() {
    setTimeout(() => (this.coming = false), 500);

    setTimeout(() => (this.live = true), 540);
    setTimeout(() => (this.live = false), 3200);

    setTimeout(() => (this.light = true), 3350);
    setTimeout(() => (this.light = false), 4570);

    setTimeout(() => (this.fire = true), 4570);
    setTimeout(() => (this.fire = false), 6310);

    setTimeout(() => (this.casser = true), 6100);
    setTimeout(() => (this.casser = false), 8470);

    setTimeout(() => (this.card = true), 8600);
    setTimeout(() => (this.card = false), 10400);

    setTimeout(() => (this.visual = true), 10200);
    setTimeout(() => (this.visual = false), 12900);

    setTimeout(() => (this.never = true), 12800);
    setTimeout(() => (this.never = false), 16200);

    setTimeout(() => (this.diamSplash = true), 16100);
    setTimeout(() => (this.diamSplash = false), 19100);

    setTimeout(() => (this.casser = true), 19100);
    setTimeout(() => (this.casser = false), 21200);

    setTimeout(() => (this.card = true), 21400);
    setTimeout(() => (this.card = false), 23200);

    setTimeout(() => (this.end = true), 22800);
    setTimeout(() => (this.end = false), 25600);
  },
};
</script>

<style scoped>
.refrain {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.slideUpLeave {
  animation: slideUp 0.3s 1.5s linear forwards;
}

.slideLeftLeave {
  animation: slideLeft 0.6s 2s linear forwards;
}

.slideRightArrive {
  animation: slideRight 0.4s linear forwards;
}

.square {
  bottom: 0;
  left: 15%;

  height: 300px;
  width: 40%;

  background: url("../assets/bg/bg-second.jpg") center center/cover;

  transform: translateY(300px);

  animation: squareAnim 0.9s forwards;
}

@keyframes slideRight {
  0% {
    transform: translateX(-100%);
  }
  100% {
    transform: translateX(0%);
  }
}

@keyframes slideLeft {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-100%);
  }
}

@keyframes slideUp {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-170%);
  }
}

@keyframes squareAnim {
  40% {
    transform: translateY(0);
    height: 300px;
  }
  60% {
    transform: translateY(-500px);
    height: 15px;
  }
  100% {
    background: #fff;
    transform: translateY(-500px) translateX(-150%);
    height: 15px;
  }
}
</style>
