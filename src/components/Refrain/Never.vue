<template>
  <div class="never">
    <div class="text index1">
      <p class="left">
        <span class="nver first">never</span>
        <span class="going first">going</span>
        <span class="back first">back</span>
      </p>
      <ul>
        <li class="grad">끝</li>
        <li class="gradStroke">내</li>
        <li class="gradStroke">주</li>
        <li class="gradStroke">지</li>
      </ul>
      <p class="right">
        <span class="nver second">never</span>
        <span class="going second">going</span>
        <span class="back second">back</span>
      </p>
    </div>

    <div class="na abs index2">
      <p class="nah">nah</p>
      <p class="not">not</p>
      <p class="that">that</p>
    </div>

    <div class="bg abs h100">
      <h1 class="gradStroke">going</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "Never",
};
</script>

<style scoped>
.never {
  position: relative;
  width: 100%;
  height: 100%;
}

.bg {
  display: flex;
  align-items: center;
  right: 0;
  bottom: 0;
}

h1 {
  text-transform: uppercase;
  -webkit-text-stroke: 1px transparent;

  font-size: 80em;
  line-height: 100%;

  animation: slowSlideRight 4s linear forwards;
}

.text {
  position: relative;

  display: flex;
  justify-content: center;
  align-items: center;
  width: 70%;
  height: 100%;
  margin: auto;
}

.text p {
  font-size: 4em;
  transform: scale(1.6);
}

p.left {
  animation: animateBackLeft 2s 0.2s forwards;
}

p.right {
  animation: animateBackRight 2s 0.2s forwards;
}

li {
  font-size: 10em;
  font-weight: bold;
  line-height: 160px;

  transform: scale(2, 1);

  animation: animateKorean 2s 0.2s forwards;
}

span {
  visibility: hidden;
  margin: 20px;
}

.nver.first {
  animation: appear 0.1s 0.1s forwards;
}

.nver.second {
  animation: appear 0.1s 0.3s forwards;
}

.going.first {
  animation: appear 0.1s 0.5s forwards;
}

.going.second {
  animation: appear 0.1s 0.7s forwards;
}

.back {
  animation: appear 0.1s 1s forwards;
}

.na {
  top: 0;
  left: 0;

  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;
}

.na p {
  font-size: 11em;
  margin-right: 50px;
  visibility: hidden;
}

.na p.nah {
  transform: translateY(50%);

  animation: appearUpFadeOne 1.3s 1.7s forwards;
}

.na p.not {
  transform: translateY(50%);

  animation: appearUpFadeTwo 1s 2s forwards;
}

.na p.that {
  transform: translateY(50%);
  background: -webkit-linear-gradient(top, #93bbec, #c3a8f9, #93bbec);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-text-stroke-width: 0;

  animation: appearUpFadeThree 0.7s 2.3s forwards;
}

@keyframes appearUpFadeOne {
  0% {
    visibility: visible;
  }
  20% {
    transform: translateY(0%);
  }
  30% {
    transform: translateY(0%);
    color: transparent;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: white;
  }
  95% {
    color: transparent;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: white;
    transform: translateY(0%);
    opacity: 1;
  }
  100% {
    color: transparent;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: white;
    transform: translateY(0%);
    opacity: 0;
  }
}

@keyframes appearUpFadeTwo {
  0% {
    visibility: visible;
  }
  20% {
    transform: translateY(0%);
  }
  30% {
    transform: translateY(0%);
    color: transparent;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: white;
  }
  97% {
    color: transparent;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: white;
    transform: translateY(0%);
    opacity: 1;
  }
  100% {
    color: transparent;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: white;
    transform: translateY(0%);
    opacity: 0;
  }
}

@keyframes appearUpFadeThree {
  0% {
    visibility: visible;
  }
  20% {
    transform: translateY(0%);
  }
  30% {
    transform: translateY(0%);
  }
  97% {
    transform: translateY(0%);
    opacity: 1;
  }
  100% {
    transform: translateY(0%);
    opacity: 0;
  }
}

@keyframes appear {
  to {
    visibility: visible;
  }
}

@keyframes animateBackLeft {
  10% {
    transform: scale(1.6) translateX(0);
  }
  30% {
    transform: scale(1.6) translateX(0);
  }
  50% {
    transform: scale(1) translateX(0);
  }
  80% {
    transform: scale(1) translateX(0);
  }
  100% {
    transform: scale(1) translateX(-200%);
  }
}

@keyframes animateBackRight {
  10% {
    transform: scale(1.6) translateX(0);
  }
  30% {
    transform: scale(1.6) translateX(0);
  }
  50% {
    transform: scale(1) translateX(0);
  }
  80% {
    transform: scale(1) translateX(0);
  }
  100% {
    transform: scale(1) translateX(200%);
  }
}

@keyframes animateKorean {
  20% {
    transform: scale(1, 1);

    background: -webkit-linear-gradient(top, #93bbec, #c3a8f9, #93bbec);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 0;
  }
  80% {
    transform: scale(1, 1);

    background: -webkit-linear-gradient(top, #93bbec, #c3a8f9, #93bbec);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 0;
  }
  100% {
    transform: scale(2, 1);
    visibility: hidden;
  }
}

@keyframes slowSlideRight {
  80% {
    transform: translateX(20%);
  }
  100% {
    transform: translateX(100%);
  }
}

@media (max-width: 1100px) {
  .text p {
    font-size: 3.5em;
  }
  span {
    margin: 15px;
  }
  h1 {
    font-size: 65em;
  }
  .na p {
    margin-right: 35px;
  }
}

@media (max-width: 800px) {
  .text p {
    font-size: 3em;
  }
  span {
    margin: 10px;
  }
  h1 {
    font-size: 110em;
  }
  .na p {
    margin-right: 25px;
  }
}

@media (max-width: 400px) {
  .text p {
    font-size: 2em;
  }
  span {
    margin: 5px;
  }

  h1 {
    font-size: 140em;
  }
  .na p {
    margin-right: 10px;
  }
}
</style>
