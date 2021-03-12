<template>
  <div class="purple">
    <div class="firstPart w150 h100 d-flex" v-if="first">
      <div class="textfirst w100 h100 d-flex">
        <p class="top" v-if="grad">
          <span class="grad">백 퍼센 </span
          ><span class="gradStroke dix">트</span>
          <span class="gradStroke deux">덤</span
          ><span class="grad">비지 못</span
          ><span class="gradStroke cinq">해</span>
          <span class="gradStroke huit">죽</span
          ><span class="grad">여주잖아</span>
        </p>
        <p class="top gradStroke" v-if="!grad">
          백 퍼센 트덤비지 못해죽여주잖아
        </p>
        <p class="mid">
          <span class="grad">백 퍼센</span
          ><span class="gradStroke treize">트</span>
          <span class="gradStroke quatre">덤</span
          ><span class="grad">비지</span> <span class="gradStroke un">못</span
          ><span class="gradStroke onze">해</span>
          <span class="gradStroke douze">죽</span
          ><span class="gradStroke trois">여</span
          ><span class="gradStroke sept">주</span><span class="grad">잖아</span>
        </p>
        <p class="bot gradStroke" v-if="!grad">
          백 퍼센 트덤비지 못해죽여주잖아
        </p>
        <p class="bot" v-if="grad">
          <span class="grad">백 퍼센 </span
          ><span class="gradStroke onze">트</span>
          <span class="gradStroke trois">덤</span
          ><span class="grad">비지 못</span
          ><span class="gradStroke six">해</span>
          <span class="gradStroke neuf">죽</span
          ><span class="grad">여주잖아</span>
        </p>
      </div>
    </div>

    <div class="secondPart w100 h100 d-flex" v-if="second">
      <div class="bgTop" v-if="red"></div>
      <div class="bgBot" v-if="red"></div>

      <p class="korBoss abs" v-if="korBoss">나는</p>
      <p class="boss abs index1" v-if="boss">boss</p>

      <div class="korSauce abs d-flex" v-if="korSauce">
        <p class="left">간</p>
        <p class="right">지</p>
      </div>
      <p class="sauce abs grad index1" v-if="sauce">sauce</p>
    </div>

    <div class="thirdPart w100 h100 d-flex" v-if="third">
      <p>원하면 줄게</p>

      <div class="squareOne abs" v-if="one"></div>
      <div class="squareTwo abs" v-if="two"></div>
      <div class="squareThird abs" v-if="three"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Purple",
  data: () => ({
    //Part
    first: true,
    second: false,
    third: false,

    //In Part 1
    grad: true,

    //In Part 2
    red: true,
    korBoss: true,
    boss: false,
    korSauce: false,
    sauce: false,

    //In Part 3
    one: false,
    two: false,
    three: false,
  }),
  created() {
    //Part
    setTimeout(() => (this.first = false), 2850);

    setTimeout(() => (this.second = true), 2850);
    setTimeout(() => (this.second = false), 5250);

    setTimeout(() => (this.third = true), 5250);

    //In Part 1
    setTimeout(() => (this.grad = false), 900);

    //In Part 2
    setTimeout(() => (this.red = true), 3350);

    setTimeout(() => (this.korBoss = false), 3850);

    setTimeout(() => (this.boss = true), 3550);
    setTimeout(() => (this.boss = false), 4550);

    setTimeout(() => (this.korSauce = true), 3850);
    setTimeout(() => (this.korSauce = false), 4550);

    setTimeout(() => (this.sauce = true), 4550);
    setTimeout(() => (this.sauce = false), 4850);

    //In Part 2
    setTimeout(() => (this.one = true), 5650);
    setTimeout(() => (this.two = true), 5850);
    setTimeout(() => (this.three = true), 6050);
  },
};
</script>

<style scoped>
.purple {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  width: 100%;
  height: 100%;

  background: #0d0a15;
}

.w150 {
  width: 150%;
}

/* First Part */
.firstPart {
  justify-content: center;
  align-items: center;

  background: #3b1471;
}

.textfirst {
  flex-direction: column;
  justify-content: center;
  align-items: center;

  transform: scale(1.7);

  animation: scaleDown 1.9s 0.1s forwards;
}

.firstPart p {
  font-weight: bold;
  font-style: italic;
}

.gradStroke {
  color: #3b1471;
}

span.gradStroke {
  animation: turnToGrad 0.1s 0.05s forwards;
}

span.gradStroke.deux {
  animation-delay: 0.15s;
}
span.gradStroke.trois {
  animation-delay: 0.2s;
}
span.gradStroke.quatre {
  animation-delay: 0.25s;
}
span.gradStroke.cinq {
  animation-delay: 0.3s;
}
span.gradStroke.six {
  animation-delay: 0.35s;
}
span.gradStroke.sept {
  animation-delay: 0.4s;
}
span.gradStroke.huit {
  animation-delay: 0.45s;
}
span.gradStroke.neuf {
  animation-delay: 0.5s;
}
span.gradStroke.dix {
  animation-delay: 0.55s;
}
span.gradStroke.onze {
  animation-delay: 0.6s;
}
span.gradStroke.douze {
  animation-delay: 0.65s;
}
span.gradStroke.treize {
  animation-delay: 0.7s;
}

p.top,
p.bot {
  transform: translateX(10%);

  animation: translateTB 0.4s forwards;
}

p.mid {
  transform: translateX(-10%);

  animation: translateMid 0.8s forwards;
}

@keyframes translateTB {
  to {
    transform: translateX(0);
  }
}

@keyframes translateMid {
  50% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(0);
    line-height: 80px;
  }
}

@keyframes turnToGrad {
  to {
    background: -webkit-linear-gradient(top, #93bbec, #c3a8f9, #93bbec);
    -webkit-background-clip: text;
    -webkit-text-stroke-width: 0;
    color: transparent;
  }
}

@keyframes scaleDown {
  5% {
    transform: scale(1);
  }
  45% {
    transform: scale(1);
  }
  50% {
    transform: scale(0.5);
  }
  80% {
    transform: scale(0.5) translateX(0);
  }
  100% {
    transform: scale(0.5) translateX(-150%);
  }
}

/* Second Part */

.secondPart {
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.bgTop,
.bgBot {
  height: 50%;
  width: 100%;

  background: #fe2725;
}

.bgTop {
  animation: slideLeft 0.3s 2s linear forwards;
}

.bgBot {
  animation: slideLeft 0.1s 2s linear forwards;
}

p.korBoss {
  font-weight: bold;

  font-style: italic;
  transform: scale(12);
  letter-spacing: 100px;

  animation: korBossAnime 1.2s forwards;
}

.korSauce p {
  letter-spacing: 0;
  font-style: normal;
  font-weight: bold;

  background: -webkit-linear-gradient(
    top,
    #93bbec 0%,
    #c3a8f9 50%,
    #93bbec 100%
  );
  -webkit-background-clip: text;
  -webkit-text-stroke: 2px transparent;
  color: #fe2725;
}

p.left {
  transform: scale(4) translateX(-200%);

  animation: korLeft 0.5s forwards;
}

p.right {
  transform: scale(4) translateX(200%);

  animation: korRight 0.5s forwards;
}

p.boss {
  color: transparent;
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: #fff;

  transform: scale(2);
  letter-spacing: 150px;
  font-style: italic;

  animation: bossAnime 0.5s forwards;
}

@keyframes korRight {
  to {
    transform: scale(4) translateX(35%);
  }
}

@keyframes korLeft {
  to {
    transform: scale(4) translateX(-35%);
  }
}

@keyframes bossAnime {
  35% {
    color: #fff;
  }
  60% {
    color: #fff;
    letter-spacing: 0;
    transform: scale(1);
  }
  100% {
    color: #fff;
    letter-spacing: 0;
    transform: scale(1);
    font-style: normal;
  }
}

@keyframes korBossAnime {
  20% {
    letter-spacing: 0;
  }
  40% {
    font-style: normal;
    transform: scale(10);
    letter-spacing: 0;

    background: -webkit-linear-gradient(top, #93bbec, #c3a8f9, #93bbec);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 0;
  }
  80% {
    transform: scale(4);
    letter-spacing: 0;
    font-style: normal;

    background: -webkit-linear-gradient(top, #93bbec, #c3a8f9, #93bbec);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 0;
  }
  100% {
    transform: scale(4);
    letter-spacing: 0;
    font-style: normal;

    background: -webkit-linear-gradient(
      top,
      #93bbec 0%,
      #c3a8f9 50%,
      #93bbec 100%
    );
    -webkit-background-clip: text;
    -webkit-text-stroke: 2px transparent;
    color: #fe2725;
  }
}

@keyframes slideLeft {
  to {
    transform: translateX(100%);
  }
}

/* Third Part */

.thirdPart {
  justify-content: center;
  align-items: center;

  animation: goRight 0.5s 0.9s ease-in forwards;
}

.thirdPart p {
  font-weight: bold;
  font-size: 6em;

  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #fff;

  transform: translateX(-250%);

  animation: slideRightKR 0.4s forwards;
}

.squareOne {
  height: 48%;
  width: 250px;

  background: url(../../assets/bg/bg-second.jpg) center center/cover;

  animation: animateOne 0.2s forwards;
}

.squareTwo {
  height: 70%;
  width: 350px;

  background: url(../../assets/bg/bg-second.jpg) center center/cover;

  transform: translateX(100%);

  animation: animateTwo 0.2s forwards;
}

.squareThird {
  height: 70%;
  width: 50%;

  transform: translateX(125%);

  background: #000;

  animation: animateThree 0.3s ease-in forwards;
}

@keyframes animateThree {
  30% {
    height: 100%;
    background: url(../../assets/bg/bg-second.jpg) center center/cover;
  }
  100% {
    height: 100%;
    background: url(../../assets/bg/bg-second.jpg) center center/cover;
    width: 100%;
  }
}

@keyframes animateTwo {
  to {
    height: 75%;
  }
}

@keyframes animateOne {
  to {
    height: 50%;
  }
}

@keyframes slideRightKR {
  to {
    transform: translateX(-100%);
    color: #fff;
  }
}

@keyframes goRight {
  to {
    transform: translateX(-125%);
  }
}

@media (max-width: 1100px) {
  p.top,
  p.bot,
  p.mid {
    font-size: 7em;
  }
}

@media (max-width: 400px) {
  p.top,
  p.bot,
  p.mid {
    font-size: 6em;
  }
  .squareOne {
    height: 48%;
    width: 100px;
  }

  .squareTwo {
    height: 70%;
    width: 250px;
  }
}
</style>
