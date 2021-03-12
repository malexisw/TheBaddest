<template>
  <div class="content">
    <div class="ill" v-if="one || two">
      <div class="grid" v-for="item in 9" :key="item">
        <div class="d-flex one" v-if="one">
          <p class="left">i'</p>
          <p class="right">ll</p>
        </div>
        <p class="two" v-if="two">be</p>
      </div>
    </div>
    <p class="here" v-if="three">here</p>
    <div class="bgMinute w100 h100 d-flex" v-if="four">
      <p class="minute">for a minute baby</p>
    </div>

    <div class="packContent" v-if="pack">
      <div class="gridPack" v-for="item in 6" :key="item">
        <p>pack your bags</p>
      </div>
    </div>

    <p class="grad" v-if="packGrad">
      <span class="pack">pack</span><span class="your">your</span>
      <span class="bags">bags</span>
    </p>
    <div class="underline" v-if="underPack"></div>

    <div class="rightBG abs" v-if="rightbg"></div>

    <div class="breaking d-flex w100 h100 abs" v-if="breaking">
      <p class="top">breaking</p>
      <p class="bot">breaking</p>
    </div>

    <div class="cut" v-if="breaking"></div>
    <p class="dark law abs" v-if="law">the law</p>
    <p class="dont abs" v-if="law">if i don't</p>
    <p class="take abs" v-if="law">got it i take</p>
  </div>
</template>

<script>
export default {
  name: "Bags",
  data: () => ({
    one: true,
    two: false,
    three: false,
    four: false,
    pack: false,
    packGrad: false,
    underPack: false,
    rightbg: false,
    breaking: false,
    law: false,
  }),
  created() {
    setTimeout(() => (this.one = false), 400);

    setTimeout(() => (this.two = true), 400);
    setTimeout(() => (this.two = false), 600);

    setTimeout(() => (this.three = true), 600);
    setTimeout(() => (this.three = false), 800);

    setTimeout(() => (this.four = true), 800);
    setTimeout(() => (this.four = false), 1700);

    setTimeout(() => (this.pack = true), 1700);
    setTimeout(() => (this.pack = false), 1900);

    setTimeout(() => (this.packGrad = true), 1900);
    setTimeout(() => (this.packGrad = false), 2300);

    setTimeout(() => (this.underPack = true), 1900);
    setTimeout(() => (this.underPack = false), 2900);

    setTimeout(() => (this.rightbg = true), 2100);
    setTimeout(() => (this.rightbg = false), 3100);

    setTimeout(() => (this.breaking = true), 2300);

    setTimeout(() => (this.law = true), 3350);
  },
};
</script>

<style scoped>
.content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  width: 100%;
  height: 100%;

  animation: scaleU 0.4s 2.8s forwards; /********************************* */
}

.ill {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  align-items: center;
  width: 100%;
  height: 100%;
}

.grid {
  text-align: center;
}

.one {
  justify-content: center;
}

.one p {
  visibility: hidden;
  animation: appearSlide 0.3s linear forwards;
}

.one p.left {
  transform: translateX(-50%);
}

.one p.right {
  transform: translateX(50%);
}

.two {
  visibility: hidden;
  transform: translateY(50%);
  animation: appearSlide 0.2s linear forwards;
}

.here {
  letter-spacing: -10px;
  animation: spaceLetter 0.2s linear forwards;
}

.bgMinute {
  flex-direction: column;
  justify-content: center;
  align-items: center;

  animation: swapBG 0.9s linear forwards;
}

.minute {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #fff;

  transform: translateY(25%);

  animation: minuteAnime 0.9s linear forwards;
}

.packContent {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  align-items: center;
  width: 130%;
  height: 80%;
  margin: auto;

  transform: translateY(-50%);
  animation: slideUp 0.2s linear forwards;
}

.gridPack p {
  font-size: 4em;
}

.grad span {
  margin-right: 20px;
  animation: disappear 0.1s forwards;
}

span.pack {
  animation-delay: 0.2s;
}

span.your {
  animation-delay: 0.35s;
}

span.bags {
  animation-delay: 0.5s;
}

.underline {
  height: 5px;
  width: 600px;

  background: linear-gradient(
    to left,
    #b5eaf2,
    #8fa3ea,
    #cfaafa,
    #a6ccf0,
    #9ca1e3
  );

  transform: translateX(-26%);

  animation: underlineAnime 1s ease-in forwards;
}

.rightBG {
  width: 50px;
  height: 75%;
  top: 0;
  right: 8%;

  background: url(../../assets/bg/bg-second.jpg) center center/cover;

  animation: rightBgAnime 1s forwards;
}

.breaking {
  flex-direction: column;
  justify-content: center;
  align-items: center;

  transform: translateX(15%);

  animation: breakSlide 0.4s 0.5s ease-out forwards;
}

.breaking p.top {
  background-image: linear-gradient(to bottom, #fff, #fff 50%, transparent 50%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-text-stroke-width: 0;
  letter-spacing: 10px;

  transform: translateY(50%);

  animation: topBreak 1.1s forwards;
}

.breaking p.bot {
  background-image: linear-gradient(
    to bottom,
    transparent,
    transparent 50%,
    #fff 50%
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-text-stroke-width: 0;
  letter-spacing: 10px;

  transform: translateY(-50%);

  animation: botBreak 1.1s forwards;
}

.cut {
  height: 15px;
  width: 60%;

  background: url(../../assets/bg/bg-second.jpg) center center/cover;

  transform: translateX(200%);

  animation: cutCome 0.6s 0.5s forwards;
}

p.law {
  font-size: 6em;
}

p.dont,
p.take {
  font-size: 4em;
}

.dont {
  top: -10%;

  animation: slideDown 1.3s 0.3s forwards;
}

.take {
  bottom: -10%;

  animation: slideTake 0.9s 0.6s forwards;
}

@keyframes slideTake {
  20% {
    bottom: 12%;
  }
  80% {
    bottom: 8%;
  }
  100% {
    bottom: 10%;
  }
}

@keyframes slideDown {
  20% {
    top: 12%;
  }
  80% {
    top: 8%;
  }
  100% {
    top: 10%;
  }
}

@keyframes cutCome {
  40% {
    transform: translateX(0);
    height: 15px;
  }
  50% {
    transform: translateX(0);
    height: 15px;
  }
  100% {
    transform: translateX(0);
    height: 50%;
  }
}

@keyframes breakSlide {
  to {
    transform: translateX(0);
  }
}

@keyframes botBreak {
  15% {
    letter-spacing: 0;
  }
  40% {
    transform: translateY(-50%);
    letter-spacing: 0;
  }
  55% {
    transform: translateY(-50%);
    letter-spacing: 10px;
  }
  80% {
    transform: translateY(-50%);
  }
  100% {
    transform: translateY(200%);
    letter-spacing: 10px;
  }
}

@keyframes topBreak {
  15% {
    letter-spacing: 0;
  }
  40% {
    transform: translateY(50%) translateX(0);
    letter-spacing: 0;
  }
  55% {
    transform: translateY(50%) translateX(-10%);
    letter-spacing: 10px;
  }
  80% {
    transform: translateY(50%) translateX(-10%);
  }
  100% {
    transform: translateY(-200%) translateX(-10%);
    letter-spacing: 10px;
  }
}

@keyframes rightBgAnime {
  20% {
    width: 200px;
    top: 0;
  }
  100% {
    top: 100%;
  }
}

@keyframes underlineAnime {
  50% {
    height: 100px;
    transform: translateX(-26%);
  }
  100% {
    height: 100px;
    transform: translateX(-200%);
  }
}

@keyframes disappear {
  to {
    visibility: hidden;
  }
}

@keyframes slideUp {
  to {
    transform: translateY(0);
  }
}

@keyframes swapBG {
  50% {
    background: #f2f0f5;
  }
  55% {
    background: var(--first-bg);
  }
  60% {
    background: #f2f0f5;
  }
  65% {
    background: var(--first-bg);
  }
  70% {
    background: #f2f0f5;
  }
  75% {
    background: var(--first-bg);
  }
  100% {
    background: var(--first-bg);
  }
}

@keyframes minuteAnime {
  20% {
    transform: translateY(0);
  }
  25% {
    transform: translateY(0);
    font-style: italic;
  }
  50% {
    transform: translateY(0);
    font-style: italic;

    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #000;
  }
  55% {
    transform: translateY(0);
    font-style: italic;

    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #fff;
  }
  60% {
    transform: translateY(0);
    font-style: italic;

    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #000;
  }
  65% {
    transform: translateY(0);
    font-style: italic;

    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #fff;
  }
  70% {
    transform: translateY(0);
    font-style: italic;

    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #000;
  }
  75% {
    transform: translateY(0);
    font-style: italic;

    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #fff;
  }
  100% {
    transform: translateY(0);
    font-style: italic;

    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #fff;
  }
}

@keyframes spaceLetter {
  to {
    letter-spacing: 0;
  }
}

@keyframes appearSlide {
  0% {
    visibility: visible;
  }
  100% {
    transform: translate(0);
    visibility: visible;
  }
}

@keyframes scaleUp {
  to {
    transform: scale(1.2);
  }
}

@media (max-width: 1100px) {
  @keyframes botBreak {
    15% {
      letter-spacing: 0;
    }
    40% {
      transform: translateY(-50%);
      letter-spacing: 0;
    }
    55% {
      transform: translateY(-50%);
      letter-spacing: 10px;
    }
    80% {
      transform: translateY(-50%);
    }
    100% {
      transform: translateY(200%);
      letter-spacing: 10px;
    }
  }
  @keyframes topBreak {
    15% {
      letter-spacing: 0;
    }
    40% {
      transform: translateY(50%) translateX(0);
      letter-spacing: 0;
    }
    55% {
      transform: translateY(50%) translateX(-10%);
      letter-spacing: 10px;
    }
    80% {
      transform: translateY(50%) translateX(-10%);
    }
    100% {
      transform: translateY(-200%) translateX(-10%);
      letter-spacing: 10px;
    }
  }
}

@media (max-width: 800px) {
  @keyframes botBreak {
    15% {
      letter-spacing: 0;
    }
    40% {
      transform: translateY(-50%);
      letter-spacing: 0;
    }
    55% {
      transform: translateY(-50%);
      letter-spacing: 10px;
    }
    80% {
      transform: translateY(-50%);
    }
    100% {
      transform: translateY(350%);
      letter-spacing: 10px;
    }
  }
  @keyframes topBreak {
    15% {
      letter-spacing: 0;
    }
    40% {
      transform: translateY(50%) translateX(0);
      letter-spacing: 0;
    }
    55% {
      transform: translateY(50%) translateX(-10%);
      letter-spacing: 10px;
    }
    80% {
      transform: translateY(50%) translateX(-10%);
    }
    100% {
      transform: translateY(-350%) translateX(-10%);
      letter-spacing: 10px;
    }
  }
}

@media (max-width: 400px) {
  p.minute {
    font-size: 7em;
  }

  @keyframes botBreak {
    15% {
      letter-spacing: 0;
    }
    40% {
      transform: translateY(-50%);
      letter-spacing: 0;
    }
    55% {
      transform: translateY(-50%);
      letter-spacing: 10px;
    }
    80% {
      transform: translateY(-50%);
    }
    100% {
      transform: translateY(450%);
      letter-spacing: 10px;
    }
  }
  @keyframes topBreak {
    15% {
      letter-spacing: 0;
    }
    40% {
      transform: translateY(50%) translateX(0);
      letter-spacing: 0;
    }
    55% {
      transform: translateY(50%) translateX(-10%);
      letter-spacing: 10px;
    }
    80% {
      transform: translateY(50%) translateX(-10%);
    }
    100% {
      transform: translateY(-450%) translateX(-10%);
      letter-spacing: 10px;
    }
  }
}
</style>
