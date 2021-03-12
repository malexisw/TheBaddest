<template>
  <div class="end">
    <img class="card abs index3" src="../../assets/Images/card.png" alt="" />

    <div class="text index2">
      <h1 class="title">that's <span>what</span></h1>
      <div class="sub d-flex">
        <p class="the">the</p>
        <p class="baddest">baddest</p>
        <p class="do">do</p>
      </div>
      <p class="decoText abs">baddest do</p>
    </div>

    <div class="small-text top abs index1">
      <ul class="static">
        <li>
          <small>we the baddest</small>
        </li>
        <li>
          <small>we the baddest</small>
        </li>
        <li>
          <small>we the baddest</small>
        </li>
      </ul>
    </div>

    <div class="small-text bot abs index1">
      <ul class="static">
        <li>
          <small>we the baddest</small>
        </li>
        <li>
          <small>we the baddest</small>
        </li>
        <li>
          <small>we the baddest</small>
        </li>
      </ul>
    </div>

    <h1 class="koreanBG abs gradStroke">끝내주지</h1>
  </div>
</template>

<script>
export default {
  name: "End",
};
</script>

<style scoped>
.end {
  height: 100%;
  width: 100%;

  display: flex;
  justify-content: center;
  align-items: center;
}

.card {
  height: 100vw;
  transform: rotate(70deg);
  top: 90%;

  animation: cardSlide 0.6s linear forwards;
}

.text {
  width: 85%;
  height: 60%;
  margin: auto;

  transform: translateY(150%);

  animation: slideUp 2s 0.1s ease-out forwards;

  position: relative;
}

.text h1 {
  line-height: 250px;
  color: #fff;
  font-size: 16em;
  text-transform: uppercase;
  font-weight: normal;

  animation: changeSize 0.001s 1s forwards;
}

.sub p {
  margin-right: 30px;
  line-height: 120px;
  font-size: 9em;

  color: transparent;
  -webkit-text-stroke-width: 0.5px;
  -webkit-text-stroke-color: white;
}

.sub {
  visibility: hidden;

  animation: appear 0.1s 0.75s forwards;
}

p.the {
  width: 60%;

  animation: widthDown 0.4s 0.8s forwards;
}

p.baddest {
  animation: widthUpDown 0.4s 0.8s linear forwards;
}

p.do {
  animation: swapColor 0.1s 1.2s forwards;
}

span {
  visibility: hidden;
  animation: appear 0.1s 0.5s forwards;
}

.decoText {
  color: transparent;
  -webkit-text-stroke-width: 0.5px;
  -webkit-text-stroke-color: white;

  font-size: 6em;

  left: 50%;
  transform: translateX(-50%) rotate(180deg);
}

.top {
  top: 5%;
}

.bot {
  bottom: 5%;
}

.small-text {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  visibility: hidden;
  animation: appear 0.1s 0.55s forwards;
}

ul {
  display: flex;
  width: 100%;
}

li {
  display: flex;
  justify-content: center;
  width: 100%;
}

small {
  display: inline-block;
  color: #fff;
  text-transform: uppercase;
  font-size: 1em;
  transform: scale(2, 1);

  filter: blur(0.4px);
}

h1.koreanBG {
  bottom: 0;
  text-transform: uppercase;
  -webkit-text-stroke: 2px transparent;

  font-size: 30em;
  line-height: 90%;

  transform: rotate(90deg) translateY(120%) translateX(0%);
  width: fit-content;
  visibility: hidden;

  animation: koreanSlideUp 0.6s 0.3s forwards;
}

@keyframes koreanSlideUp {
  0% {
    visibility: visible;
  }
  100% {
    visibility: hidden;
    transform: rotate(90deg) translateY(120%) translateX(-28%);
  }
}

@keyframes swapColor {
  to {
    color: #fff;
  }
}

@keyframes widthUpDown {
  50% {
    color: transparent;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: white;
    width: 60%;
  }
  75% {
    color: #fff;
  }
  100% {
    color: #fff;
    width: 450px;
  }
}

@keyframes widthDown {
  50% {
    color: #fff;
    width: 40%;
  }
  100% {
    color: #fff;
    width: 190px;
  }
}

@keyframes changeSize {
  to {
    font-size: 9em;
    line-height: 150px;
  }
}

@keyframes appear {
  to {
    visibility: visible;
  }
}

@keyframes cardSlide {
  to {
    transform: rotateX(90deg) rotateY(-20deg) rotateZ(60deg);
    top: -160%;
  }
}

@keyframes slideUp {
  50% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(0);
    height: 45%;
  }
}

@media (max-width: 1100px) {
  .sub p {
    margin-right: 0px;
    line-height: 120px;
    font-size: 9em;
  }

  @keyframes widthUpDown {
    50% {
      color: transparent;
      -webkit-text-stroke-width: 0.5px;
      -webkit-text-stroke-color: white;
      width: 60%;
    }
    75% {
      color: #fff;
    }
    100% {
      color: #fff;
      width: 400px;
    }
  }

  @keyframes widthDown {
    50% {
      color: #fff;
      width: 40%;
    }
    100% {
      color: #fff;
      width: 170px;
    }
  }
  p.decoText{
    font-size: 5em;
    left: 80%;
    width: 50%;
  }
}

@media (max-width: 800px) {
  @keyframes widthUpDown {
    50% {
      color: transparent;
      -webkit-text-stroke-width: 0.5px;
      -webkit-text-stroke-color: white;
      width: 60%;
    }
    75% {
      color: #fff;
    }
    100% {
      color: #fff;
      width: 320px;
    }
  }

  @keyframes widthDown {
    50% {
      color: #fff;
      width: 40%;
    }
    100% {
      color: #fff;
      width: 140px;
    }
  }
}

@media (max-width: 400px) {
  p.decoText{
    font-size: 5em;
    left: 80%;
    width: 50%;
  }
}
</style>
