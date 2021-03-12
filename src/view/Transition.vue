<template>
  <div class="transition w100 h100">
    <div class="textBG abs">
      <div class="bg-damage center d-flex" v-if="damage">
        <p class="abs bg-i">i'm</p>
        <p class="abs bg-doing">doing</p>
        <p class="abs bg-dmg">damage</p>
      </div>
      <p class="bg-planned abs" v-if="planned">how i p</p>
      <p class="bg-want" v-if="want">i want</p>
      <p class="bg-one" v-if="one">두 날 따</p>
      <p class="bg-two" v-if="two">끝내주잖</p>
      <div class="bg-insane center d-flex" v-if="insane">
        <p class="bg-to abs">to</p>
        <p class="bg-live abs">live</p>
        <p class="bg-on abs">on</p>
        <p class="bg-the abs">the</p>
        <p class="bg-edge abs">edge</p>
        <p class="bg-of abs">of</p>
        <p class="bg-isn abs">insane</p>
      </div>
    </div>
    <div class="textFront center d-flex index1">
      <div class="damage d-flex" v-if="damage">
        <p class="i dark ">
          <span class="one">i</span><span class="two">'m</span>
        </p>
        <p class="doing dark ">
          <span class="five">d</span><span class="three">o</span
          ><span class="seven">i</span><span class="six">n</span
          ><span class="four">g</span>
        </p>
        <p class="dmg dark">
          <span class="height">d</span><span class="nine">a</span
          ><span class="ten">m</span><span class="twelve">a</span
          ><span class="height">g</span><span class="eleven">e</span>
        </p>
      </div>
      <p class="planned dark" v-if="planned">went just how i planned it</p>
      <div class="want dark d-flex abs" v-if="want">
        <p class="dark i1">i</p>
        <p class="dark do">do</p>
        <p class="dark what">what</p>
        <p class="dark i2">i</p>
        <p class="dark want">want</p>
        <p class="dark when">when</p>
        <p class="dark i3">i</p>
        <p class="dark say">say</p>
      </div>
      <p class="kor one dark" v-if="one">
        <span class="quatre">모</span><span class="six">두</span>
        <span class="trois">날</span> <span class="trois">따</span
        ><span class="cinq">라</span> <span class="un">해</span>
      </p>
      <p class="kor two dark" v-if="two">
        <span class="quatre">난</span> <span class="six">끝</span
        ><span class="trois">내</span><span class="deux">주</span
        ><span class="cinq">잖</span><span class="un">아</span>
      </p>
      <div class="insane dark d-flex" v-if="insane">
        <p class="to dark">to</p>
        <p class="live dark">live</p>
        <p class="on dark">on</p>
        <p class="the dark">the</p>
        <p class="edge dark">edge</p>
        <p class="of dark">of</p>
        <p class="isn dark">insane</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Transition",
  data: () => ({
    damage: true,
    planned: false,
    want: false,
    one: false,
    two: false,
    insane: false,
  }),
  created() {
    setTimeout(() => (this.damage = false), 1300);

    setTimeout(() => (this.planned = true), 1350);
    setTimeout(() => (this.planned = false), 3000);

    setTimeout(() => (this.want = true), 2900);
    setTimeout(() => (this.want = false), 5900);

    setTimeout(() => (this.one = true), 5900);
    setTimeout(() => (this.one = false), 7600);

    setTimeout(() => (this.two = true), 7600);
    setTimeout(() => (this.two = false), 8950);

    setTimeout(() => (this.insane = true), 9350);
  },
};
</script>

<style scoped>
.transition {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  background: url(../assets/bg/bg-second.jpg) center center/cover;
}

.textBG,
.center {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  width: 100%;
  height: 100%;
}

p {
  font-size: 4em;
}

.kor p {
  font-size: 6em;
}

.damage p {
  transform: translateY(-50%);
  margin-right: 20px;
  animation: slideDown 0.3s linear forwards;
}

p.doing {
  animation-delay: 0.2s;
}

p.dmg {
  animation-delay: 0.6s;
}

.damage span {
  visibility: hidden;
  animation: appear 0.1s forwards;
}

span.two {
  animation-delay: 0.2s;
}
span.three {
  animation-delay: 0.25s;
}
span.four {
  animation-delay: 0.3s;
}
span.five {
  animation-delay: 0.4s;
}
span.six {
  animation-delay: 0.45s;
}
span.seven {
  animation-delay: 0.5s;
}
span.height {
  animation-delay: 0.65s;
}
span.nine {
  animation-delay: 0.7s;
}
span.ten {
  animation-delay: 0.75s;
}
span.eleven {
  animation-delay: 0.8s;
}
span.twelve {
  animation-delay: 0.85s;
}

.textBG p {
  color: transparent;
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: #fff;

  font-size: 30em;
}

.bg-damage p,
.bg-insane p {
  visibility: hidden;

  animation: appear 0.15s 1;
}

p.bg-doing {
  animation-delay: 0.2s;
  animation-duration: 0.3s;
}

p.bg-dmg {
  animation-delay: 0.6s;
  animation-duration: 0.6s;
}

.planned {
  letter-spacing: 25px;
  animation: spaceLetter 1.5s linear forwards;
}

.bg-planned {
  opacity: 0;
  letter-spacing: 25px;
  animation: spaceFadeOut 1s linear forwards;
}

.textFront .want.d-flex {
  letter-spacing: 30px;
  animation: spaceLetter 3s linear forwards;
}

.want p {
  margin-right: 20px;
  animation: fadeIn 0.1s forwards;
  opacity: 0;
}

.want .do {
  animation-delay: 0.1s;
}
.want .what {
  animation-delay: 0.2s;
}
.want .i2 {
  animation-delay: 0.3s;
}
.want .want {
  animation-delay: 0.4s;
}
.want .when {
  animation-delay: 0.5s;
}
.want .i3 {
  animation-delay: 0.6s;
}
.want .say {
  animation-delay: 0.7s;
}

.bg-want {
  letter-spacing: 30px;
  opacity: 0;
  animation: spaceFadeOut 1.5s 0.5s linear forwards;
}

.kor {
  font-weight: bold;
}

.kor.one,
.kor.two {
  letter-spacing: 30px;
  animation: spaceLetter 1.7s linear forwards;
}

.kor.one span,
.kor.two span {
  opacity: 0;
  animation: fadeIn 0.1s forwards;
}

.kor.one span.deux,
.kor.two span.deux {
  animation-delay: 0.1s;
}
.kor.one span.trois,
.kor.two span.trois {
  animation-delay: 0.2s;
}
.kor.one span.quatre,
.kor.two span.quatre {
  animation-delay: 0.3s;
}
.kor.one span.cinq,
.kor.two span.cinq {
  animation-delay: 0.4s;
}
.kor.one span.six,
.kor.two span.six {
  animation-delay: 0.5s;
}

.bg-one {
  opacity: 0;
  letter-spacing: 30px;
  animation: spaceFadeOut 1.3s 0.1s linear forwards;
}

p.bg-two {
  font-size: 25em;
  letter-spacing: 15px;
  opacity: 0;
  animation: spaceFadeOut 1.3s 0.1s linear forwards;
}

.insane p {
  transform: translateY(-50%);
  margin-right: 20px;
  animation: slideDownAppear 0.3s linear forwards;
  visibility: hidden;
}

.insane p.live {
  animation-delay: 0.25s;
}
.insane p.on {
  animation-delay: 0.6s;
}
.insane p.the {
  animation-delay: 0.8s;
}
.insane p.edge {
  animation-delay: 1s;
}
.insane p.of {
  animation-delay: 1.3s;
}
.insane p.isn {
  animation-delay: 1.5s;
}

p.bg-live {
  animation-delay: 0.2s;
  animation-duration: 0.3s;
}
p.bg-on {
  animation-delay: 0.5s;
  animation-duration: 0.2s;
}
p.bg-the {
  animation-delay: 0.7s;
  animation-duration: 0.2s;
}
p.bg-edge {
  animation-delay: 0.9s;
  animation-duration: 0.3s;
}
p.bg-of {
  animation-delay: 1.2s;
  animation-duration: 0.2s;
}
p.bg-isn {
  animation-delay: 1.4s;
  animation-duration: 0.7s;
}

@keyframes slideDownAppear {
  0% {
    visibility: visible;
  }
  100% {
    visibility: visible;
    transform: translateY(0);
  }
}

@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

@keyframes spaceFadeOut {
  10% {
    opacity: 1;
  }
  80% {
    opacity: 1;
  }
  100% {
    letter-spacing: 0;
    opacity: 0;
  }
}

@keyframes spaceLetter {
  to {
    letter-spacing: 0;
  }
}

@keyframes slideDown {
  to {
    transform: translateY(0);
  }
}

@keyframes appear {
  0% {
    visibility: visible;
  }
  100% {
    visibility: visible;
  }
}

@media (max-width: 1100px) {
  .textBG p {
    font-size: 20em;
  }
  p.bg-two {
    font-size: 15em;
  }
  p.bg-one {
    letter-spacing: 20px;
    font-size: 15em;
  }
  .kor.one,
  .kor.two {
    letter-spacing: 20px;
  }
  .planned {
    letter-spacing: 15px;
  }
}

@media (max-width: 800px) {
  .planned {
    letter-spacing: 10px;
  }
  .insane p {
    margin-right: 10px;
  }
}

@media (max-width: 400px) {
  .planned {
    letter-spacing: 5px;
  }
  .insane p {
    margin-right: 5px;
  }
  .damage p {
    margin-right: 10px;
  }
  .textBG p {
    font-size: 15em;
  }
  p.bg-two {
    font-size: 12em;
  }
  p.bg-one {
    letter-spacing: 5px;
    font-size: 12em;
  }
}
</style>
