<template>
  <div class="byteContain">
    <div class="bgImg abs h100 w100"></div>
    <div class="bg h100 w100 abs d-flex index1">
      <div class="bgtop"></div>
      <div class="bgbot"></div>
    </div>

    <p class="dark index2" v-if="subByte">
      <span v-if="dis">byte byte byte byte b</span>yte byte byt<span v-if="dis"
        >e byte byte byte byte</span
      >
    </p>
    <p class="byte index2" v-if="byte">byte</p>
    <p class="big index2" v-if="big">믿어봐 큰 만큼 크게</p>
    <p class="kor index2" v-if="kor">어깨 펴고</p>

    <p class="high gradStroke abs" v-if="kor">ig</p>
  </div>
</template>

<script>
export default {
  name: "Byte",
  data: () => ({
    dis: true,
    subByte: true,
    byte: false,
    big: false,
    kor: false,
  }),
  created() {
    setTimeout(() => (this.dis = false), 100);
    setTimeout(() => (this.subByte = false), 200);

    setTimeout(() => (this.byte = true), 200);
    setTimeout(() => (this.byte = false), 500);

    setTimeout(() => (this.big = true), 500);
    setTimeout(() => (this.big = false), 2680);

    setTimeout(() => (this.kor = true), 2400);
  },
};
</script>

<style scoped>
.byteContain {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  width: 100%;
  height: 100%;

  background: var(--first-bg);

  animation: changeBG 0.2s forwards;
}

.bgImg {
  background: url(../../assets/Images/BG_Rap1.png) center center/cover;

  animation: slideRight 0.5s 2.2s linear forwards;
}

.bg {
  flex-direction: column;
}

.bg .bgtop,
.bg .bgbot {
  height: 50%;
  width: 100%;

  background: #d21416;
}

.bg .bgtop {
  animation: slideUp 0.4s 0.5s linear forwards;
}

.bg .bgbot {
  animation: slideDown 0.4s 0.5s linear forwards;
}

p.dark {
  font-size: 3em;

  word-spacing: 40px;
}

p.byte {
  color: transparent;
  background: url(../../assets/bg/bike.jpg) center no-repeat;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-text-stroke-width: 0;

  font-size: 15em;
}

p.big {
  font-weight: bold;
  font-size: 6em;

  letter-spacing: 80px;

  animation: resetSpace 2.18s linear forwards;
}

p.kor {
  font-weight: bold;

  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #fff;

  letter-spacing: 200px;

  animation: lastAnime 0.4s forwards;

  font-size: 12em;
}

p.high {
  font-size: 125em;
  font-style: italic;

  width: 100%;
  letter-spacing: 100px;

  animation: minSlideLeft 1.5s forwards;
}

@keyframes minSlideLeft {
  to {
    transform: translateX(-10%);
  }
}

@keyframes lastAnime {
  80% {
    letter-spacing: 0;
    visibility: hidden;
  }
  85% {
    visibility: hidden;
    transform: scale(1);
    color: transparent;
  }
  90% {
    visibility: hidden;
    transform: scale(0.5);
  }
  100% {
    transform: scale(0.5);
    letter-spacing: 0;
    visibility: visible;
    color: white;
  }
}

@keyframes slideRight {
  to {
    transform: translateX(-100%);
  }
}

@keyframes slideUp {
  to {
    transform: translateY(-100%);
  }
}

@keyframes slideDown {
  to {
    transform: translateY(100%);
  }
}

@keyframes resetSpace {
  36% {
    letter-spacing: 0;
  }
  77% {
    transform: translateY(0);
    letter-spacing: 0;
  }
  100% {
    transform: translateY(-400%);
    letter-spacing: 0;
  }
}
</style>
