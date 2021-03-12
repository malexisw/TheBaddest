<template>
  <div class="litContain">
    <div class="abs lit h100 w100" v-if="lit">
      <p class="top abs"><span>나는</span> lit</p>
      <p class="mid"><span>나는</span> lit</p>
      <p class="bot abs"><span>나는</span> lit</p>
    </div>

    <div class="abs bit h100 w100" v-if="bit">
      <p class="behind gradStroke abs"><span>크게 </span> like a</p>
      <p class="forward index1">bit</p>
    </div>

    <div class="abs korean h100 w100" v-if="kor">
      <p class="left gradStroke abs"><span>그거 말고</span></p>
      <p class="center gradStroke"><span>그거 말고</span></p>
      <p class="right gradStroke abs"><span>그거 말고</span></p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Lit",
  data: () => ({
    lit: true,
    bit: false,
    kor: false,
  }),
  created() {
    setTimeout(() => (this.lit = true), 200);
    setTimeout(() => (this.lit = false), 900);

    setTimeout(() => (this.bit = true), 900);
    setTimeout(() => (this.bit = false), 1300);

    setTimeout(() => (this.kor = true), 1300);
  },
};
</script>

<style scoped>
.litContain {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  width: 100%;
  height: 100%;

  background: #ff283f;

  animation: changeBG 0.2s forwards;
}

.lit,
.bit,
.korean {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.lit {
  animation: scaleDown 0.1s 0.5s forwards;
}

.bot {
  bottom: 5%;
}

.top {
  top: 5%;
}

.left {
  left: 5%;
}

.right {
  right: 5%;
}

span {
  font-weight: bold;
}

p.top,
p.bot {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #fff;

  letter-spacing: 200px;

  animation: resetSpace 0.6s forwards;
}

p.mid {
  color: transparent;
  background: url(../../assets/bg/bike.jpg) center no-repeat;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-text-stroke-width: 0;

  letter-spacing: 30px;

  animation: resetSpace 0.3s forwards;
}

p.behind {
  -webkit-text-stroke-width: 0.5px;

  font-size: 11em;

  letter-spacing: 80px;

  animation: resetSpace 0.4s forwards;
}

p.forward {
  color: transparent;
  background: url(../../assets/bg/bike.jpg) center no-repeat;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-text-stroke-width: 0;

  transform: scale(0.6);
}

.korean p {
  visibility: hidden;
  transform: scale(0.6) translateY(50%);
  font-style: italic;

  animation: fadeUp 0.2s forwards;
}

p.left {
  animation-delay: 0.2s;
}

p.right {
  animation-delay: 0.4s;
}

@keyframes fadeUp {
  0% {
    visibility: visible;
  }
  50% {
    visibility: visible;
    transform: scale(0.6) translateY(0);

    background: -webkit-linear-gradient(
      top,
      #93bbec 0%,
      #c3a8f9 50%,
      #93bbec 100%
    );
    -webkit-background-clip: text;
    -webkit-text-stroke: 0.5px transparent;
    color: var(--first-bg);
  }
  100% {
    visibility: visible;
    transform: scale(0.6) translateY(0);

    color: transparent;
    background: url(../../assets/bg/bike.jpg) center no-repeat;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 0;
  }
}

@keyframes scaleDown {
  to {
    transform: scale(0.6);
  }
}

@keyframes resetSpace {
  to {
    letter-spacing: 0;
  }
}

@keyframes changeBG {
  to {
    background: #0d0a11;
  }
}

@media (max-width: 1100px) {
  p.left,p.right,p.center {
    font-size: 6.5em;
  }
}

@media (max-width: 400px) {
  p.left,p.right,p.center {
    font-size: 5em;
  }
}
</style>
