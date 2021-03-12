<template>
  <div class="content">
    <p class="kor abs" v-if="first">
      <span class="one">언</span><span class="two">제</span
      ><span class="three">든</span><span class="four space">지</span
      ><span class="five">내</span><span class="six space">가</span
      ><span class="seven space">좀</span><span class="height">해</span>
    </p>
    <p class="kor stroke abs" v-if="first">언제든지 내가 좀 해</p>

    <div class="h100 w100 d-flex center second abs" v-if="second">
      <div class="red abs"></div>
      <p class="kor dark abs index2">언제든지</p>
      <div class="akaFrame abs index1"></div>
    </div>

    <div class="akaFrameBot index1 abs" v-if="second"></div>
    <p class="gold dark abs index2" v-if="second">the gold all on my chest</p>

    <p class="look index2" v-if="third">
      l<span class="o1">o</span><span class="o2">o</span
      ><span class="k">k</span>
    </p>

    <p class="goldW index2" v-if="fourth">
      at <span class="the">the</span><span class="or">gold</span>
    </p>

    <div class="w100 h100 d-flex center abs last" v-if="last">
      <p class="call abs">
        call
      </p>
      <p class="it abs">
        it
      </p>
      <p class="a abs">
        a
      </p>
      <p class="flex grad abs">
        flex
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Impress",
  data: () => ({
    first: true,
    second: false,
    third: false,
    fourth: false,
    last: false,
  }),
  created() {
    setTimeout(() => (this.first = false), 1000);

    setTimeout(() => (this.second = true), 1000);
    setTimeout(() => (this.second = false), 3300);

    setTimeout(() => (this.third = true), 3300);
    setTimeout(() => (this.third = false), 3600);

    setTimeout(() => (this.fourth = true), 3600);
    setTimeout(() => (this.fourth = false), 4100);

    setTimeout(() => (this.last = true), 4100);
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

  transform: translateX(-100%);

  animation: slideR 0.3s forwards;
}

span.space {
  margin-right: 35px;
}

p.kor {
  font-weight: bold;
}

p.stroke {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #fff;

  transform: translateY(200%);
  visibility: hidden;

  animation: strokeAnime 0.3s 0.25s forwards;
}

.kor span {
  visibility: hidden;
  animation: appear 0.1s forwards;
}

span.one {
  animation-delay: 0.3s;
}
span.two {
  animation-delay: 0.35s;
}
span.three {
  animation-delay: 0.4s;
}
span.four {
  animation-delay: 0.45s;
}
span.five {
  animation-delay: 0.5s;
}
span.six {
  animation-delay: 0.6s;
}
span.seven {
  animation-delay: 0.6s;
}
span.height {
  animation-delay: 0.65s;
}

.second {
  transform: translateX(-100%);
  animation: slideR2 1s forwards;
}

.red {
  width: 48%;
  height: 100%;
  right: 0;

  background: #fb161d;
}

p.kor.dark {
  font-size: 15em;
  right: 16%;
  top: 10%;

  animation: changeColor 0.1s 0.15s forwards;
}

.akaFrame {
  height: 35%;
  width: 57%;
  background: url(../../assets/bg/bg-second.jpg) center center/cover;

  left: 2%;
  top: 17%;

  animation: toRight0 0.3s 0.3s forwards;
}

.center {
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.akaFrameBot {
  height: 35%;
  width: 50%;
  background: url(../../assets/bg/bg-second.jpg) center center/cover;

  left: -100%;
  bottom: 17%;

  animation: akaAnime 2.3s 0.1s forwards;
}

p.gold {
  font-size: 4em;
  padding: 0 80px;
  background: url(../../assets/bg/bg-second.jpg) center center/cover;

  visibility: hidden;

  animation: appearGold 1.1s 1.2s forwards;
}

p.look {
  color: #dcd6e2;
  font-size: 25em;
}

p.look span {
  visibility: hidden;
  animation: appear 0.1s forwards;
}

p.look span.k {
  animation-delay: 0.05s;
}
p.look span.o2 {
  animation-delay: 0.1s;
}
p.look span.o1 {
  animation-delay: 0.15s;
}

p.goldW {
  color: #dcd6e2;
  font-size: 12em;
}

p.goldW span {
  margin-right: 20px;
  visibility: hidden;
  animation: appear 0.1s forwards;
}

p.goldW span.the {
  animation-delay: 0.05s;
}
p.goldW span.or {
  animation-delay: 0.25s;
}

.last p {
  visibility: hidden;
  animation: showTime;
}

.last p.call {
  animation-delay: 0s;
  animation-duration: 0.2s;
  color: #dcd6e2;
  font-size: 25em;
}
.last p.it {
  animation-delay: 0.2s;
  animation-duration: 0.15s;
  color: #dcd6e2;
  font-size: 25em;
}
.last p.a {
  animation-delay: 0.35s;
  animation-duration: 0.1s;
  color: #dcd6e2;
  font-size: 25em;
}
.last p.flex {
  animation-delay: 0.45s;
  animation-duration: 2s;
  font-size: 55em;
}

@keyframes showTime {
  0% {
    visibility: visible;
  }
  100% {
    visibility: visible;
  }
}

@keyframes appearGold {
  0% {
    visibility: visible;
    line-height: 50px;
  }
  20% {
    line-height: 50px;
  }
  95% {
    visibility: hidden;
  }
  100% {
    visibility: hidden;
  }
}

@keyframes akaAnime {
  35% {
    left: 50%;
    transform: translateX(-50%);
    height: 35%;
    width: 50%;
  }
  50% {
    left: 50%;
    transform: translateX(-50%);
    height: 80%;
    width: 70%;
  }
  90% {
    left: 50%;
    bottom: 8%;
    transform: translateX(-50%);
    height: 75%;
    width: 70%;
  }
  100% {
    left: 10%;
    transform: translateX(-50%);
    height: 75%;
    width: 0;
  }
}

@keyframes toRight0 {
  to {
    transform: translateX(70%);
  }
}

@keyframes changeColor {
  to {
    color: #dcd6e2;
  }
}

@keyframes strokeAnime {
  0% {
    visibility: visible;
  }
  100% {
    transform: translateY(0);
    visibility: visible;
  }
}

@keyframes appear {
  to {
    visibility: visible;
  }
}

@keyframes slideR2 {
  20% {
    transform: translateX(0);
  }
  60% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(100%);
  }
}

@keyframes slideR {
  to {
    transform: translateX(0);
  }
}

@media (max-width: 1100px) {
  p.kor {
    font-size: 7em;
  }
  .last p.flex {
    font-size: 45em;
  }
}

@media (max-width: 800px) {
  p.gold {
    padding: 0 40px;
  }
}

@media (max-width: 400px) {
  p.kor {
    font-size: 5em;
  }
  .last p.flex {
    font-size: 35em;
  }
  p.gold {
    padding: 0 5px;
  }
}
</style>
