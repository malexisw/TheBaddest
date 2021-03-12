<template>
  <div class="intro h100 w100">
    <!-- Text component -->
    <div v-if="slideVisible" class="index2">
      <Slidedown />
    </div>

    <div class="abs d-flex index2" v-if="doVisible">
      <p class="D">d</p>
      <p class="O">o</p>
    </div>

    <div class="abs d-flex index2" v-if="scale">
      <Textscale />
    </div>

    <div class="cut abs d-flex" v-if="koreanT">
      <div class="left bg d-flex ">
        <p class="korean">
          끝내
        </p>
      </div>
      <div class="right bg d-flex ">
        <p class="korean">
          주지
        </p>
      </div>
    </div>

    <div class="d-flex abs baddFade index2" v-if="slideText">
      <p class="textAppear left d-flex">
        the <span class="B">b</span>a<span class="D">d</span>
      </p>

      <p class="textAppear right d-flex">d<span class="E">e</span>st</p>
    </div>

    <div class="baddest d-flex abs" v-if="textLogo">
      <div class="left d-flex">
        <div class="square">
          <p class="the">The</p>
        </div>
        <p class="B2">b</p>
        <p class="A">a</p>
        <p class="D1">d</p>
      </div>
      <div class="right d-flex">
        <p class="D2">d</p>
        <p class="E2">e</p>
        <p class="S">s</p>
        <p class="T">t</p>
      </div>
    </div>

    <!-- Image component -->
    <div class="logo" v-if="logo1"></div>

    <div class="abs d-flex index2" v-if="logo2slide">
      <LogoSlide2 />
    </div>

    <div class="logo ori1 abs index2" v-if="logoOri1"></div>

    <div class="abs d-flex index2" v-if="logo4slide">
      <LogoSlide4 />
    </div>

    <div class="logo ori3 abs index1" v-if="logo3"></div>

    <!-- Background component -->
    <div class="bg-up" v-if="bgFirst">
      <img src="../assets/bg/bg-second.jpg" alt="" />
    </div>

    <div class="bg-scale" v-if="bgSecond">
      <img src="../assets/bg/bg-second.jpg" alt="" />
    </div>

    <div class="bgSquare abs d-flex" v-if="slideText">
      <div id="left"></div>
      <div id="right"></div>
    </div>

    <!-- Deco component -->
    <div class="abs d-flex index1" v-if="liKr">
      <LiKorean />
    </div>

    <div class="abs t5 w100" v-if="smallSlide">
      <SmallText direction="droite" />
    </div>

    <div class="abs b5 w100" v-if="smallSlide">
      <SmallText direction="gauche" />
    </div>

    <div class="abs b5 w100 index1" v-if="smallStatic">
      <SmallText direction="static" />
    </div>

    <div class="abs t5 w100 index1" v-if="smallStatic">
      <SmallText direction="static" />
    </div>
  </div>
</template>

<script>
import Slidedown from "../components/Intro/Slidedown";
import Textscale from "../components/Intro/Textscale.vue";

import LiKorean from "../components/Intro/LiKorean.vue";
import SmallText from "../components/Intro/SmallText.vue";

import LogoSlide2 from "../components/Intro/LogoSlide2.vue";
import LogoSlide4 from "../components/Intro/LogoSlide4.vue";

export default {
  name: "Intro",
  components: {
    Slidedown,
    Textscale,
    LogoSlide2,
    LogoSlide4,
    LiKorean,
    SmallText,
  },
  data: () => ({
    //Text Variable
    slideVisible: false,
    doVisible: false,
    logoOri1: false,
    scale: false,
    koreanT: false,
    slideText: false,
    textLogo: false,
    liKr: false,
    smallSlide: false,
    smallStatic: false,

    //BG variable
    bgFirst: false,
    bgSecond: false,

    //Img animation
    logo1: true,
    logo2slide: false,
    logo4slide: false,
    logo3: false,
  }),
  created() {
    //Text Timeout
    setTimeout(() => (this.slideVisible = true), 500);
    setTimeout(() => (this.slideVisible = false), 1700);
    setTimeout(() => (this.slideVisible = true), 2270);
    setTimeout(() => (this.slideVisible = false), 2950);
    setTimeout(() => (this.slideVisible = true), 7400);
    setTimeout(() => (this.slideVisible = false), 7750);

    setTimeout(() => (this.doVisible = true), 2950);
    setTimeout(() => (this.doVisible = false), 4200);

    setTimeout(() => (this.scale = true), 5300);
    setTimeout(() => (this.scale = false), 6150);

    setTimeout(() => (this.koreanT = true), 7300);
    setTimeout(() => (this.koreanT = false), 8400);

    setTimeout(() => (this.slideText = true), 8500);
    setTimeout(() => (this.slideText = false), 10450);

    setTimeout(() => (this.textLogo = true), 10200);
    setTimeout(() => (this.textLogo = false), 13000);

    //Background timeout
    setTimeout(() => (this.bgFirst = true), 500);
    setTimeout(() => (this.bgFirst = false), 2500);

    setTimeout(() => (this.bgSecond = true), 4480);
    setTimeout(() => (this.bgSecond = false), 6100);

    //Img animation
    setTimeout(() => (this.logo1 = false), 500);

    setTimeout(() => (this.logo2slide = true), 1440);
    setTimeout(() => (this.logo2slide = false), 2270);

    setTimeout(() => (this.logoOri1 = true), 4970);
    setTimeout(() => (this.logoOri1 = false), 5500);

    setTimeout(() => (this.logo4slide = true), 6170);
    setTimeout(() => (this.logo4slide = false), 6850);

    setTimeout(() => (this.logo3 = true), 8150);
    setTimeout(() => (this.logo3 = false), 8450);

    //Deco animation

    setTimeout(() => (this.liKr = true), 590);
    setTimeout(() => (this.liKr = false), 1560);
    setTimeout(() => (this.liKr = true), 2950);
    setTimeout(() => (this.liKr = false), 6150);
    setTimeout(() => (this.liKr = true), 9260);
    setTimeout(() => (this.liKr = false), 10290);

    setTimeout(() => (this.smallSlide = true), 8000);
    setTimeout(() => (this.smallSlide = false), 9860);

    setTimeout(() => (this.smallStatic = true), 10360);
    setTimeout(() => (this.smallStatic = false), 12900);
  },
};
</script>

<style scoped>
.intro {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.logo {
  display: block;
  height: 500px;
  width: 500px;

  background: no-repeat url("../assets/white/logo1.png") center center/cover;

  animation: swap-bg 0.5s forwards;
}

.logo.ori1 {
  transform: translateY(-20%);
  background: no-repeat url("../assets/original/logo1.png") center center/cover;
  animation: appearLogo 0.5s forwards;
}

.logo.ori3 {
  background: no-repeat url("../assets/original/logo3.png") center center/cover;
  animation: appearLogo3 0.4s forwards;
  transform: scale(1.8);
}

.bg-up {
  position: absolute;
  width: 85%;
  height: 80%;

  bottom: -80%;

  animation: slideUp 0.6s forwards;

  z-index: 0;
}

.bg-up img,
.bg-scale img {
  width: 100%;
  height: 100%;
}

.D {
  position: relative;
  right: 5px;
  animation: letterSpaceRight 0.5s forwards;
}

.O {
  position: relative;
  left: 5px;
  animation: letterSpaceLeft 0.5s forwards;
}

.bg-scale {
  position: absolute;
  width: 100%;
  height: 100%;

  transform: scale(0.2);

  animation: scaleBgUp 0.7s forwards;

  z-index: 0;
}

.cut {
  align-items: center;

  width: 100%;
  height: 100%;

  transform: scale(1.1);
  background: url("../assets/bg/bg-second.jpg") center center/cover;

  animation: scaleDown 0.8s ease-out forwards;
}

.cut p {
  font-size: 5em;
  font-weight: 600;
}

.cut .left {
  background: var(--first-bg);
  height: 100%;
  width: 50%;
  justify-content: flex-end;
  align-items: center;
  animation: slideUpKT 0.5s 0.5s forwards;
}

.cut .right {
  background: var(--first-bg);
  height: 100%;
  width: 50%;
  justify-content: flex-start;
  align-items: center;
  animation: slideDownKT 0.5s 0.5s forwards;
}

.bgSquare {
  width: 65%;
  height: 95%;

  animation: HandW 0.35s forwards;
}

.textAppear.right {
  width: 45%;
  justify-content: flex-start;

  animation: slideUpT 0.7s 1.2s forwards;
}

.textAppear.left {
  width: 55%;
  justify-content: flex-end;

  animation: slideDownT 0.7s 1.2s forwards;
}

.textAppear {
  color: var(--first-bg);
}

.baddFade {
  align-items: center;

  width: 100%;
  height: 100%;

  letter-spacing: 20px;
  transform: scale(2);

  animation: closeScale 0.6s 0.2s forwards;
}

span {
  opacity: 0;
}

span.D {
  animation: fadeIn 0.1s forwards;
}

span.E {
  animation: fadeIn 0.1s 0.1s forwards;
}

span.B {
  margin-left: 25px;
  animation: fadeIn 0.1s 0.2s forwards;
}

#left,
#right {
  width: 50%;
  height: 100%;
}
#right {
  background: no-repeat url("../assets/bg/right-bg.jpg") center center/cover;
  animation: slideUpKT 0.5s 1.2s forwards;
}
#left {
  background: no-repeat url("../assets/bg/left-bg.jpg") center center/cover;
  animation: slideDownKT 0.5s 1.2s forwards;
}

.baddest {
  height: 100%;
  width: 100%;
  justify-content: center;
}

.baddest p {
  font-size: 15em;
}

.baddest .left {
  height: 100%;
  width: 50%;
  align-items: center;
  justify-content: flex-end;
  background: var(--first-bg);
  animation: slideLeft 0.5s 2.3s forwards;
}

.baddest .right {
  height: 100%;
  width: 50%;
  align-items: center;
  justify-content: flex-start;
  background: var(--first-bg);
  animation: slideRight 0.5s 2.3s forwards;
}

.left p,
.right p {
  animation: letterSpace 0.5s 2.1s forwards;
}

.square {
  background: linear-gradient(0.2turn, #cadfe2, #93bbec);
  width: 125px;
  height: 206px;
  position: relative;
  left: 10px;
  transform: translateY(-2px);
}

.square p {
  letter-spacing: 0;
  font-size: 1.5em;
  color: var(--first-bg);
  padding: 10px;

  animation: hideText 0.1s 2.3s forwards;
}

.left .B2 {
  background: -webkit-linear-gradient(#93bbec, #9fc3e7);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.left .A {
  background: -webkit-linear-gradient(#acc9e7, #a0b1e5);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.left .D1 {
  background: -webkit-linear-gradient(#c3a8f9, #9ab2ee);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.right .D2 {
  background: -webkit-linear-gradient(#9195f0, #a1b2f7);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.right .E2,
.right .S,
.right .T {
  background: -webkit-linear-gradient(#8d91f4, #96a2ee);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.t5 {
  top: 5%;
}

.b5 {
  bottom: 5%;
}

/* Animations */

@keyframes swap-bg {
  12.5% {
    background: no-repeat url("../assets/white/logo2.png") center center/cover;
  }
  25% {
    background: no-repeat url("../assets/white/logo3.png") center center/cover;
  }
  37.5% {
    background: no-repeat url("../assets/white/logo4.png") center center/cover;
  }
  50% {
    background: no-repeat url("../assets/white/logo1.png") center center/cover;
  }
  62.5% {
    background: no-repeat url("../assets/white/logo2.png") center center/cover;
  }
  75% {
    background: no-repeat url("../assets/white/logo3.png") center center/cover;
  }
  87.5% {
    background: no-repeat url("../assets/white/logo4.png") center center/cover;
  }
  100% {
    background: transparent;
  }
}

@keyframes letterSpaceLeft {
  80% {
    left: -2px;
  }
  100% {
    left: -2px;
  }
}

@keyframes letterSpaceRight {
  80% {
    right: -2px;
  }
  100% {
    right: -2px;
  }
}

@keyframes appearLogo {
  50% {
    transform: translateY(0%);
  }
  100% {
    transform: scale(0) translateY(0%);
  }
}

@keyframes slideUp {
  50% {
    bottom: 50%;
    transform: translateY(50%);
    width: 85%;
    height: 80%;
  }
  90% {
    bottom: 50%;
    transform: translateY(50%);
    width: 85%;
    height: 80%;
  }
  100% {
    bottom: 50%;
    transform: translateY(50%);
    width: 100%;
    height: 100%;
  }
}

@keyframes scaleBgUp {
  to {
    transform: scale(1);
  }
}

@keyframes scaleDown {
  70% {
    transform: scale(1);
    background: url("../assets/bg/bg-second.jpg") center center/cover;
  }
  100% {
    transform: scale(1);
    background: var(--first-bg);
  }
}

@keyframes slideUpKT {
  to {
    transform: translateY(-120%);
  }
}

@keyframes slideDownKT {
  to {
    transform: translateY(120%);
  }
}

@keyframes appearLogo3 {
  to {
    transform: scale(0.8);
  }
}

@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

@keyframes closeScale {
  50% {
    letter-spacing: 0;
    transform: scale(2);
  }
  100% {
    letter-spacing: 0;
    transform: scale(1);
  }
}

@keyframes HandW {
  30% {
    height: 100%;
    width: 65%;
  }
  100% {
    height: 100%;
    width: 100%;
  }
}

@keyframes slideUpT {
  to {
    transform: translateY(-300%);
  }
}

@keyframes slideDownT {
  to {
    transform: translateY(300%);
  }
}

@keyframes hideText {
  to {
    visibility: hidden;
  }
}

@keyframes letterSpace {
  100% {
    letter-spacing: 100px;
  }
}

@keyframes slideLeft {
  to {
    transform: translateX(-120%);
  }
}

@keyframes slideRight {
  to {
    transform: translateX(120%);
  }
}

@media (max-width: 1100px) {
  .square {
    width: 105px;
    height: 167px;
    transform: translateY(-1px);
  }
}

@media (max-width: 800px) {
  .square {
    width: 85px;
    height: 130px;
    transform: translateY(-1px);
  }
}

@media (max-width: 400px) {
  .square {
    width: 45px;
    height: 78px;
  }
}
</style>
