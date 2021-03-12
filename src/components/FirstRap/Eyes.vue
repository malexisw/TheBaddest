<template>
  <div class="eyes w100 h100 d-flex">
    <div class="back h100 w100"></div>
    <p class="abs">
      <span class="second">a</span><span class="first">l</span
      ><span class="third space">l</span><span class="fourth">t</span
      ><span class="second">h</span><span class="sixth space">e</span>
      <span class="first">e</span><span class="sixth">y</span
      ><span class="second">e</span><span class="fifth space">s</span>
      <span class="fifth">o</span><span class="third space">n</span>
      <span class="fourth">m</span><span class="first">e</span>
    </p>
  </div>
</template>

<script>
export default {
  name: "Eyes",
};
</script>

<style scoped>
.eyes {
  width: 100%;
  height: 100%;

  justify-content: center;
  align-items: center;
}

p {
  color: #9abcfb;
  font-size: 8em;
  letter-spacing: 20px;

  animation: spaceLetter 1s forwards;
}

span {
  opacity: 0;
  animation: fadeIn 0.05s linear forwards;
}

span.space {
  margin-right: 20px;
}

span.second {
  animation-delay: 0.05s;
}
span.third {
  animation-delay: 0.1s;
}
span.fourth {
  animation-delay: 0.15s;
}
span.fifth {
  animation-delay: 0.2s;
}
span.sixth {
  animation-delay: 0.25s;
}

.back {
  background: var(--first-bg);
  animation: goLeft 1.2s linear forwards;
  transform: translateX(100%);
}

@keyframes spaceLetter {
  40% {
    color: #9abcfb;
  }
  100% {
    color: #b70110;
    letter-spacing: 0px;
  }
}

@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

@keyframes goLeft {
  20% {
    transform: translateX(0);
    background: var(--first-bg);
  }
  100% {
    transform: translateX(0);
    background: linear-gradient(to right bottom, var(--first-bg) 30%, #b70110);
  }
}

@media (max-width: 400px) {
  p {
    font-size: 7em;
  }
}
</style>
