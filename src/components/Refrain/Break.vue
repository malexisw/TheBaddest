<template>
  <div class="break">
    <div class="title">
      <h1 class="gradStroke under">
        break
      </h1>
      <h1 class="hover abs">
        <span class="B">b</span><span class="R">r</span><span class="E">e</span
        ><span class="A">a</span><span class="K">k</span>
      </h1>
    </div>
    <div class="rules abs w100 d-flex" v-if="rules">
      <p class="left">r</p>
      <p id="mid">rules</p>
      <p class="right">s</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Break",
  data: () => ({
    rules: false,
  }),
  created() {
    setTimeout(() => (this.rules = true), 800);
  },
};
</script>

<style scoped>
.break {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  animation: slideUp 0.6s 1.7s forwards;
}

.title {
  text-align: center;
  width: 100%;
}

h1 {
  width: 100%;
  font-weight: normal;
  font-size: 40em;
  text-transform: uppercase;
}

.under {
  transform: translateX(100%);
  font-style: italic;
  letter-spacing: 100px;
  animation: slideLeft 0.5s forwards;
}

.hover {
  top: 50%;
  transform: translateY(-55%);
  left: 2%;

  display: block;
  width: 100%;
  font-style: italic;

  background: -webkit-linear-gradient(top, #b3f3ff, #adceef, #ded9d6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-text-stroke-width: 0;
}

span {
  visibility: hidden;
}

span.B {
  animation: appear 1s 0.5s forwards;
}

span.R {
  animation: appear 0.95s 0.55s forwards;
}

span.E {
  animation: appear 0.9s 0.6s forwards;
}

span.A {
  animation: appear 0.85s 0.65s forwards;
}

span.K {
  animation: appear 0.8s 0.7s forwards;
}

.rules {
  text-align: center;
  background: var(--first-bg);
  line-height: 200px;

  animation: widthChange 0.1s 0.5s forwards;
}

.right,
#mid,
.left {
  font-size: 12rem;
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: white;
}

#mid {
  text-align: center;
  width: 97%;

  animation: colorChange 0.15s forwards;
}

#mid::before {
  width: 40%;
  content: " ";
  position: absolute;
  background: var(--first-bg);
  left: 0px;
  bottom: 50%;
  transform: translateY(49%);
  height: 165px;

  border-top: 1px solid #fff;
  border-bottom: 1px solid #fff;

  z-index: 1;

  animation: goRightBefore 1s forwards;
}

.left {
  position: absolute;
  left: 0;

  animation: goRight 1s forwards;
}

#mid::after {
  width: 41.5%;
  content: " ";
  position: absolute;
  background: var(--first-bg);
  right: 0;
  bottom: 50%;
  transform: translateY(49%);
  height: 165px;
  border-top: 1px solid #fff;
  border-bottom: 1px solid #fff;
  z-index: 1;

  animation: goLeftAfter 1s forwards;
}

.right {
  position: absolute;
  right: 0;

  animation: goLeft 1s forwards;
}

@keyframes appear {
  1% {
    visibility: visible;
  }
  99% {
    visibility: visible;
  }
  100% {
    visibility: hidden;
  }
}

@keyframes slideLeft {
  to {
    letter-spacing: 0;
    transform: translateX(0);
  }
}

@keyframes goRightBefore {
  50% {
    background: #fff;
  }
  100% {
    background: #fff;
    left: 40%;
    width: 0px;
  }
}

@keyframes goRight {
  50% {
    color: #fff;
  }
  100% {
    color: #fff;
    left: 39%;
    opacity: 0;
  }
}

@keyframes goLeftAfter {
  50% {
    background: #fff;
  }
  100% {
    background: #fff;
    right: 40%;
    width: 0px;
  }
}

@keyframes goLeft {
  50% {
    color: #fff;
  }
  100% {
    color: #fff;
    right: 39%;
    opacity: 0;
  }
}

@keyframes colorChange {
  50% {
    color: transparent;
  }
  100% {
    color: #fff;
  }
}

@keyframes widthChange {
  to {
    width: fit-content;
    background: transparent;
  }
}

@keyframes slideUp {
  to {
    transform: translateY(-100%);
  }
}

@media (max-width: 1100px) {
  h1 {
    font-size: 30em;
  }
  .rules {
    line-height: 120px;
  }

  .right,
  #mid,
  .left {
    font-size: 10rem;
  }
  #mid::after {
    height: 110px;
  }
  #mid::before {
    height: 110px;
  }
}

@media (max-width: 800px) {
  h1 {
    font-size: 25em;
  }
  .rules {
    line-height: 90px;
  }

  .right,
  #mid,
  .left {
    font-size: 9rem;
  }
  #mid::after {
    height: 80px;
  }
  #mid::before {
    height: 80px;
  }
}

@media (max-width: 400px) {
  h1 {
    font-size: 20em;
  }

  .rules {
    line-height: 50px;
  }

  .right,
  #mid,
  .left {
    font-size: 8rem;
  }

  #mid::after {
    height: 40px;
  }
  #mid::before {
    height: 40px;
  }
}
</style>
