<template>
  <div class="bad">
    <p class="ba abs">bad</p>
    <div class="arrow index2 abs"></div>
    <p class="B bg abs" v-if="bad">b</p>
    <p class="A bg abs" v-if="bad">a</p>
    <p class="D bg abs" v-if="bad">d</p>
    <p class="minute abs index3" v-if="text">
      <span class="only">only</span><span class="took">took</span>
      <span class="a">a</span><span class="minute">minute</span>
      <span class="for">for</span><span class="me">me</span>
      <span class="to">to</span><span class="get">get</span>
      <span class="what">what</span><span class="you">you</span>
      <span class="had">had</span>
    </p>

    <div class="bgWhite abs index1"></div>
    <div class="bgGrad abs index1" v-if="bgGrad"></div>
    <div class="bgBlack abs index2"></div>

    <div class="sorryContain abs w100 h100 index1" v-if="sor">
      <h1 class="sorryText grad">sorry</h1>
      <div class="cut abs d-flex">
        <p class="soz">
          <span class="for">for</span><span class="the">the</span>
          <span class="bd">bad</span><span class="news">news</span>
          <span class="know">know</span><span class="it">it</span>
          <span class="makes">makes</span><span class="you">you</span>
          <span class="sad">sad</span>
        </p>
      </div>
    </div>

    <div class="bg abs" v-if="sor">
      <p v-if="FT">for the</p>
      <p v-if="BN">bad news</p>
      <p v-if="KI">know it</p>
      <p v-if="MK">makes</p>
      <p v-if="YS">you sad</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Bad",
  data: () => ({
    bg: true,
    text: true,
    bgGrad: true,
    bad: true,
    sor: false,

    //data bg sorry
    FT: false,
    BN: false,
    KI: false,
    MK: false,
    YS: false,
  }),
  created() {
    setTimeout(() => (this.bg = false), 300);
    setTimeout(() => (this.bad = false), 2600);
    setTimeout(() => (this.text = false), 3500);
    setTimeout(() => (this.bgGrad = false), 4100);

    setTimeout(() => (this.sor = true), 4100);
    setTimeout(() => (this.FT = true), 4450);
    setTimeout(() => (this.FT = false), 4650);

    setTimeout(() => (this.BN = true), 4650);
    setTimeout(() => (this.BN = false), 5500);

    setTimeout(() => (this.KI = true), 5500);
    setTimeout(() => (this.KI = false), 6100);

    setTimeout(() => (this.MK = true), 6100);
    setTimeout(() => (this.MK = false), 6450);

    setTimeout(() => (this.YS = true), 6450);
    setTimeout(() => (this.YS = false), 6900);
    setTimeout(() => (this.sor = false), 6900);
  },
};
</script>

<style scoped>
.bad {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  width: 100%;
  height: 100%;

  background: #f2f0f5;

  animation: changeBG 0.1s 0.2s forwards;
}

p.ba {
  text-transform: uppercase;
  font-size: 30em;

  color: transparent;
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: var(--first-bg);

  animation: badTxtAnime 0.4s linear forwards;
}

.arrow {
  width: 100%;
  height: 100px;

  background: -webkit-linear-gradient(
    left,
    #6ea1be,
    #b2c4dc,
    #7076c0,
    #96c6d4,
    #bdbed3,
    #6d7cbf,
    #8cbdce,
    #8995bf
  );

  transform: translateX(-100%);
  animation: slideRightDown 2.2s 0.2s linear forwards;
}

p.minute {
  font-size: 4em;

  animation: changeColorScale 0.3s 2.2s forwards;
}

p.minute span {
  margin-right: 20px;
  visibility: hidden;
  animation: appear 0.1s forwards;
}

p.minute span.only {
  animation-delay: 1s;
}
p.minute span.took {
  animation-delay: 1.3s;
}
p.minute span.a {
  animation-delay: 1.5s;
}
p.minute span.minute {
  animation-delay: 1.6s;
}
p.minute span.for {
  animation-delay: 2s;
}
p.minute span.me {
  animation-delay: 2.05s;
}
p.minute span.to,
p.minute span.get {
  animation-delay: 2.5s;
}
p.minute span.what {
  animation-delay: 2.8s;
}
p.minute span.you {
  animation-delay: 3s;
}
p.minute span.had {
  animation-delay: 3.1s;
}

p.bg {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #fff;
}

p.B {
  font-size: 60em;
  line-height: 600px;
  left: 28%;
  bottom: 0;

  animation: Banime 2.25s 0.45s forwards;
}

p.A {
  visibility: hidden;
  font-size: 35em;
  animation: appear 0.1s 0.6s forwards;
}

p.D {
  line-height: 420px;
  font-size: 30em;
  bottom: 0;
  right: 10%;
  visibility: hidden;

  animation: appear 0.1s 0.5s forwards;
}

.bgWhite {
  top: 0;

  background: #ddd8dc;

  animation: swapBG 1s 2.4s linear forwards;
}

.bgGrad {
  height: 35%;
  width: 0;
  transform: translateY(-20%);

  background: url(../../assets/bg/bg-second.jpg) center center/cover;

  animation: appearBg 0.9s 3.2s forwards;
}

.bgBlack {
  height: 30%;
  width: 50%;
  transform: translateY(10%);
  visibility: hidden;

  background: #181623;

  animation: bgGoUp 0.6s 3.5s forwards;
}

@keyframes bgGoUp {
  0% {
    visibility: visible;
  }
  95% {
    transform: translateY(-55%);
    visibility: visible;
  }
  100% {
    transform: translateY(-55%);
    visibility: hidden;
  }
}

@keyframes appearBg {
  20% {
    width: 60%;
    transform: translateY(-20%);
  }
  100% {
    width: 60%;
    transform: translateY(40%);
  }
}

@keyframes swapBG {
  15% {
    height: 100%;
    width: 60%;
  }
  30% {
    width: 100%;
    height: 100%;
  }
  70% {
    transform: translateY(0);
    width: 100%;
    height: 100%;
  }
  100% {
    transform: translateY(100%);
    width: 100%;
    height: 100%;
  }
}

@keyframes Banime {
  5% {
    transform: scale(1.1);
  }
  15% {
    left: 0;
    bottom: 40%;
    transform: scale(0.5);
    line-height: 210px;
  }
  20% {
    left: -5%;
    bottom: 40%;
    transform: scale(0.4);
    line-height: 210px;
    visibility: visible;
  }
  65% {
    left: -5%;
    bottom: 40%;
    transform: scale(0.4);
    line-height: 210px;
    visibility: hidden;
  }
  78% {
    bottom: 10%;
    left: 5%;
    transform: scale(0.4);
    line-height: 210px;
    visibility: hidden;
  }
  80% {
    bottom: 10%;
    left: 5%;
    transform: scale(0.4);
    line-height: 210px;
    visibility: visible;
  }
  100% {
    bottom: -10%;
    left: 5%;
    transform: scale(0.4);
    line-height: 210px;
    visibility: visible;
  }
}

@keyframes changeColorScale {
  to {
    transform: scale(0.8);
    color: var(--first-bg);
  }
}

@keyframes appear {
  to {
    visibility: visible;
  }
}

@keyframes slideRightDown {
  40% {
    transform: translateX(0);
  }
  90% {
    transform: translateY(0) translateX(0);
  }
  100% {
    transform: translateY(550%) translateX(0);
  }
}

@keyframes changeBG {
  to {
    background: var(--first-bg);
  }
}

@keyframes badTxtAnime {
  25% {
    transform: scale(0.9);
  }
  30% {
    transform: scale(0.2);
    color: var(--first-bg);
  }
  75% {
    transform: scale(0.2);
    color: #f2f0f5;
  }
  100% {
    transform: scale(0.2);
    color: #f2f0f5;
    visibility: hidden;
  }
}

/*Sorry Part */

.sorryContain {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  animation: scaleDown 0.1s 0.3s forwards;
}

h1.sorryText {
  text-transform: uppercase;
  font-size: 25em;
  font-weight: 100;
  transform: scale(1, 0);

  animation: scaleUp 0.5s linear forwards;
}

.cut {
  height: 100px;
  width: 100%;
  background: var(--first-bg);
}

.cut p.soz {
  width: 100%;
  text-align: center;
  font-size: 4em;
}

.cut p.soz span {
  margin-right: 20px;
  visibility: hidden;
  animation: appear 0.1s forwards;
}

.cut p.soz span.the {
  animation-delay: 0.4s;
}

.cut p.soz span.bd {
  animation-delay: 0.6s;
}

.cut p.soz span.news {
  animation-delay: 0.95s;
}

.cut p.soz span.know {
  animation-delay: 1.45s;
}

.cut p.soz span.it {
  animation-delay: 1.7s;
}

.cut p.soz span.makes {
  animation-delay: 1.9s;
}

.cut p.soz span.you {
  animation-delay: 2.1s;
}

.cut p.soz span.sad {
  animation-delay: 2.25s;
}

.bg p {
  font-size: 20em;

  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #fff;
}

@keyframes scaleUp {
  to {
    transform: scale(1, 1);
  }
}

@keyframes scaleDown {
  to {
    transform: scale(0.4);
  }
}

@media (max-width: 1100px) {
  p.minute span {
    margin-right: 10px;
  }
  .cut {
    height: 80px;
  }
}

@media (max-width: 800px) {
  p.minute span {
    margin-right: 10px;
  }
  .cut {
    height: 60px;
  }
}

@media (max-width: 400px) {
  p.minute span {
    margin-right: 5px;
  }
  .cut {
    height: 40px;
  }
  .bg p {
    font-size: 16em;
  }
  .cut p.soz span {
    margin-right: 5px;
  }
}
</style>
