<template>
  <div class="whoaSection">
    <div class="whoa">
      <p class="textW abs" v-if="whoa">whoa</p>
      <div class="darkStroke d-flex textK" v-if="kali">
        <p class="ka">ka</p>
        <p class="li">li</p>
      </div>
      <p class="dark textG" v-if="goat">goat</p>
    </div>

    <div class="korean abs" v-if="korea">
      <p>난 알지</p>
      <p>난 알지</p>
    </div>

    <div class="korean2 abs" v-if="korea2">
      <p>난 알지</p>
      <p>난 알지</p>
      <p>난 알지</p>
    </div>

    <div class="top abs w100 index1" v-if="smallText">
      <SmallTextWhoa direction="droite" />
    </div>

    <div class="bot abs w100 index1" v-if="smallText">
      <SmallTextWhoa direction="gauche" />
    </div>
  </div>
</template>

<script>
import SmallTextWhoa from "./smallTextWhoa.vue";

export default {
  name: "Whoa",
  components: {
    SmallTextWhoa,
  },
  data: () => ({
    smallText: true,
    whoa: true,
    kali: false,
    goat: false,
    korea: false,
    korea2: false,
  }),
  created() {
    setTimeout(() => (this.kali = true), 200);
    setTimeout(() => (this.whoa = false), 900);
    setTimeout(() => (this.kali = false), 1200);
    setTimeout(() => (this.goat = true), 1200);
    setTimeout(() => (this.goat = false), 1800);

    setTimeout(() => (this.korea = true), 1800);
    setTimeout(() => (this.korea = false), 2000);

    setTimeout(() => (this.korea2 = true), 1950);
  },
};
</script>

<style scoped>
.whoaSection {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  width: 100%;
  height: 100%;

  background: #fe2725;

  animation: changeBG 0.1s 2.1s forwards;
}

.whoa {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  position: relative;

  width: 100%;
  height: 100%;
}

.textW {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #000;

  transform: scale(4);
  letter-spacing: 50px;
  text-align: center;

  animation: whoaAnime 0.3s linear forwards;
}

.textK {
  animation: scaleDown 0.1s 0.9s forwards;
}

.textK p {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #000;

  font-size: 15em;
  line-height: 150px;
}

.textK p.ka {
  transform: translateX(-400%);
  letter-spacing: 50px;

  animation: kaliAnime 0.8s forwards;
}

.textK p.li {
  transform: translateX(550%);
  letter-spacing: 50px;
  animation: kaliAnime 0.8s forwards;
}

.textG {
  letter-spacing: 250px;

  animation: goatAnime 0.3s forwards;
}

.korean {
  left: 5%;

  transform: translateY(40%);

  animation: translateY0 0.2s forwards;
}

.korean p {
  font-weight: bold;
  font-size: 18em;
  line-height: 1.5em;
  color: transparent;
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: #fff;
}

.korean2 {
  left: 10%;
  opacity: 0;

  animation: korean2Anime 1.1s forwards;
}

.korean2 p {
  font-weight: bold;
  font-size: 14em;
  line-height: 1.1em;

  animation: fadeInandOut 0.3s 0.1s forwards;
}

@keyframes changeBG {
  to {
    background: #000;
  }
}

@keyframes fadeInandOut {
  20% {
    opacity: 0.5;
  }
  40% {
    opacity: 1;
  }
  70% {
    opacity: 0.5;
    color: #fff;
  }
  100% {
    opacity: 1;
    color: #000;
  }
}

@keyframes korean2Anime {
  10% {
    opacity: 1;
  }
  90% {
    transform: scale(1);
  }
  100% {
    opacity: 1;
    transform: scale(0);
  }
}

@keyframes translateY0 {
  to {
    transform: translateY(0);
  }
}

@keyframes goatAnime {
  to {
    letter-spacing: 0;
    transform: scale(0.8);
  }
}

@keyframes scaleDown {
  100% {
    transform: scale(0.5);
  }
}

@keyframes kaliAnime {
  90% {
    color: transparent;
  }
  100% {
    transform: translateX(0);
    letter-spacing: 0px;
    color: #000;
  }
}

@keyframes whoaAnime {
  90% {
    color: transparent;
  }
  100% {
    transform: scale(1) translateY(-90%);
    letter-spacing: 0px;
    color: #000;
  }
}

.bot {
  bottom: 5%;
}

.top {
  top: 5%;
}
</style>
