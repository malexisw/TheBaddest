<template>
  <div class="light d-flex">
    <ul>
      <li>
        <p class="gradStroke stretch">light it</p>
        <p class="U gradStroke">u</p>
        <p class="P gradStroke">p</p>
      </li>
      <li>
        <p class="gradStroke stretch">light it</p>
        <p class="U gradStroke">u</p>
        <p class="P gradStroke">p</p>
      </li>
      <li>
        <p class="gradStroke stretch">light it</p>
        <p class="U gradStroke">u</p>
        <p class="P gradStroke">p</p>
      </li>
      <li>
        <p class="gradStroke stretch">light it</p>
        <p class="U gradStroke">u</p>
        <p class="P gradStroke">p</p>
      </li>
      <li class="space">
        <p class="grad stretch">light it</p>
        <p class="U grad">u</p>
        <p class="P grad">p</p>
      </li>
      <li>
        <p class="gradStroke stretch">light it</p>
        <p class="U gradStroke">u</p>
        <p class="P gradStroke">p</p>
      </li>
      <li>
        <p class="gradStroke stretch">light it</p>
        <p class="U gradStroke">u</p>
        <p class="P gradStroke">p</p>
      </li>
      <li>
        <p class="gradStroke stretch">light it</p>
        <p class="U gradStroke">u</p>
        <p class="P gradStroke">p</p>
      </li>
      <li>
        <p class="gradStroke stretch">light it</p>
        <p class="U gradStroke">u</p>
        <p class="P gradStroke">p</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Light",
};
</script>

<style scoped>
li {
  line-height: 140px;
  display: flex;
}

.space {
  animation: lineHeight 0.85s 0.7s forwards;
}

.stretch {
  transform: scale(2.5, 1);

  animation: descale 0.25s forwards;
}

.U {
  margin-left: 25px;
  transform: translateY(300%);
}

.P {
  transform: translateY(400%);
}

.U,
.P {
  animation: transform 0.5s 0.25s forwards;
}

@keyframes lineHeight {
  50% {
    margin: 50vh 0;
  }
  80% {
    margin: 50vh 0;
  }
  100% {
    margin: 50vh 0;
    transform: translateY(-400%);
  }
}

@keyframes descale {
  to {
    transform: scale(1, 1);
  }
}

@keyframes transform {
  to {
    transform: translateY(0%);
  }
}

@media (max-width: 1100px) {
  li {
    line-height: 130px;
  }
}

@media (max-width: 800px) {
  li {
    line-height: 110px;
  }
  @keyframes lineHeight {
    50% {
      margin: 50vh 0;
    }
    80% {
      margin: 50vh 0;
    }
    100% {
      margin: 50vh 0;
      transform: translateY(-550%);
    }
  }
}

@media (max-width: 400px) {
  li {
    line-height: 80px;
  }
  @keyframes lineHeight {
    50% {
      margin: 50vh 0;
    }
    80% {
      margin: 50vh 0;
    }
    100% {
      margin: 50vh 0;
      transform: translateY(-550%);
    }
  }
}
</style>
