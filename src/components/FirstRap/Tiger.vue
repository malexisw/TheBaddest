<template>
  <div class="d-flex w100 h100 container">
    <img class="abs" src="../../assets/Images/Tiger.png" alt="Tiger" />
    <div class="koreanText d-flex" v-if="koreanT">
      <p class="left"><span>걸</span>어<span>들</span></p>
      <p class="right">어<span>와</span></p>
    </div>
    <div class="slideUp abs"></div>
    <div class="slideRight abs"></div>

    <div class="koreanText2 abs d-flex">
      <div class="topLeft d-flex">
        <p class="firstLetter">유</p>
        <p class="secondLetter">행</p>
      </div>
      <p class="rightBot">선두자</p>
    </div>

    <p class="lastText abs dark index2">애가 타잖아</p>
    <div class="lastBg abs index1"></div>
  </div>
</template>

<script>
export default {
  name: "Tiger",
  data: () => ({
    koreanT: true,
    koreanT2: false,
  }),
  created() {
    setTimeout(() => (this.koreanT = false), 1100);

    /*setTimeout(() => this.cut = true, 3200)
        setTimeout(() => this.cut = false, 4800)*/
  },
};
</script>

<style scoped>
.container {
  justify-content: center;
  align-items: center;

  background: #ff283f;
}

img {
  max-width: 100%;
  max-height: 100%;
  width: auto;
  height: auto;

  transform: scale(4);

  animation: scaleDown 0.7s forwards;
}

p {
  font-size: 6em;
  font-weight: bold;
}

.koreanText p {
  visibility: hidden;

  animation: KRText 0.8s 0.2s linear forwards;
}

.koreanText p.left {
  transform: translateX(-300%) scale(2);
}

.koreanText p.right {
  transform: translateX(300%) scale(2);
}

.koreanText p span {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: white;
  animation: colored 0.6s 0.2s forwards;
}

.koreanText2 p {
  font-size: 20em;
  letter-spacing: -20px;
}

.koreanText2 .topLeft p {
  color: transparent;
  background: url(../../assets/bg/bike.jpg) center no-repeat;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-text-stroke-width: 0;
}

.koreanText2 .topLeft {
  opacity: 1;
  animation: disapear 0.1s 2.1s forwards;
}

.koreanText2 .topLeft .firstLetter {
  transform: translateY(200%);
  animation: slideUpFirstLetter 0.5s 1s linear forwards;
}

.koreanText2 .topLeft .secondLetter {
  visibility: hidden;
  animation: slideUpSecondLetter 0.5s 1.2s linear forwards;
}

.koreanText2 p.rightBot {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: white;

  transform: translateY(200%);

  animation: slideUpBotLetter 1s 1.4s linear forwards;
}

.slideUp {
  height: 80%;
  width: 100%;

  background: url("../../assets/bg/bg-second.jpg") center center/cover;

  top: 100%;

  animation: slideUp 0.5s 1s linear forwards;
}

.slideRight {
  height: 100%;
  width: 17%;

  background: url("../../assets/bg/bg-second.jpg") center center/cover;

  left: -20%;

  animation: slideBG 3s 1.3s linear forwards;
}

p.lastText {
  font-size: 5em;
  left: 20%;
  bottom: 25%;

  transform: scale(3);
  letter-spacing: 50px;
  visibility: hidden;

  animation: lastTextAnime 0.7s 3.6s ease-out forwards;
}

.lastBg {
  width: 0%;
  height: 0%;

  background: url(../../assets/bg/bg-second.jpg) center center/cover;

  animation: lastBgAnime 1.2s 4s linear forwards;
}

@keyframes lastBgAnime {
  0% {
    width: 40%;
    height: 20%;
  }
  30% {
    height: 70%;
  }
  40% {
    height: 70%;
    width: 70%;
  }
  70% {
    height: 70%;
    width: 70%;
  }
  100% {
    height: 0%;
    width: 70%;
    bottom: 15%;
  }
}

@keyframes lastTextAnime {
  0% {
    visibility: visible;
  }
  100% {
    visibility: visible;
    transform: scale(1);
    letter-spacing: 0px;
  }
}

@keyframes disapear {
  to {
    opacity: 0;
  }
}

@keyframes slideUpSecondLetter {
  0% {
    visibility: hidden;
  }
  100% {
    visibility: visible;
    transform: translateY(-35%);
  }
}

@keyframes slideUpBotLetter {
  35% {
    transform: translateY(35%);
  }
  70% {
    transform: translateY(35%);
    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: white;
  }
  85% {
    transform: translateY(35%);
    color: #000;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #000;
  }
  90% {
    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #000;
    transform: translateY(35%);
  }
  100% {
    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #000;
    transform: translateY(150%);
  }
}

@keyframes slideUpFirstLetter {
  to {
    transform: translateY(-35%);
  }
}

@keyframes slideBG {
  10% {
    left: 20px;
    width: 17%;
  }
  30% {
    left: 20px;
    width: 17%;
    transform: translateX(0%);
  }
  45% {
    left: 50%;
    transform: translateX(-50%);
    width: 80%;
    height: 100%;
  }
  83% {
    left: 50%;
    transform: translateX(-50%);
    width: 80%;
    height: 100%;
  }
  100% {
    left: 50%;
    transform: translateX(-50%);
    width: 80%;
    height: 0;
  }
}

@keyframes slideUp {
  to {
    top: -100%;
  }
}

@keyframes colored {
  50% {
    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #000;
  }
  100% {
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #000;
    color: #000;
  }
}

@keyframes KRText {
  0% {
    visibility: visible;
  }
  30% {
    transform: translateX(0);
  }
  100% {
    visibility: visible;
    transform: scale(1) translateX(0);
    color: #000;
  }
}

@keyframes scaleDown {
  to {
    transform: scale(0);
  }
}
</style>
