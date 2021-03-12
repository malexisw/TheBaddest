<template>
  <div class="d-flex center">
    <div class="boys d-flex" v-if="boys">
      <p class="textL">boys</p>
      <p class="textR">on me</p>
    </div>
    <div class="line" v-if="line">
      <p class="textM">lines on ring</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Boys",
  data: () => ({
    boys: true,
    line: false,
  }),
  created() {
    setTimeout(() => (this.boys = false), 1500);

    setTimeout(() => (this.line = true), 1500);
  },
};
</script>

<style scoped>
.center {
  justify-content: center;
  align-items: center;
}

p {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: white;
}

.textL {
  margin-right: 35px;

  transform: scale(2) translateX(-150%);

  animation: animeLeftText 1.5s ease-in-out forwards;
}

.textR {
  transform: scale(2) translateX(180%);

  animation: animeRightText 1.3s 0.2s ease-in-out forwards;
}

.textM {
  transform: scale(2);
  letter-spacing: 90px;

  animation: animeMidText 1.5s ease-in-out forwards;
}

@keyframes animeMidText {
  20% {
    transform: scale(1);
    letter-spacing: 0;
  }
  30% {
    transform: scale(1);
    letter-spacing: 0;
    color: white;
  }
  90% {
    transform: scale(1);
    letter-spacing: 0;
    color: white;
  }
  100% {
    color: white;
    letter-spacing: 0;
    transform: scale(0);
  }
}

@keyframes animeLeftText {
  20% {
    transform: scale(1) translateX(0);
  }
  30% {
    transform: scale(1) translateX(0);
    color: white;
  }
  90% {
    transform: scale(1) translateX(0);
    color: white;
  }
  95% {
    color: transparent;
  }
  100% {
    color: transparent;
    transform: scale(1) translateX(-60%);
  }
}

@keyframes animeRightText {
  20% {
    transform: scale(1) translateX(0);
  }
  30% {
    transform: scale(1) translateX(0);
    color: white;
  }
  90% {
    transform: scale(1) translateX(0);
    color: white;
  }
  95% {
    color: transparent;
  }
  100% {
    color: transparent;
    transform: scale(1) translateX(60%);
  }
}

@media (max-width: 1100px) {
}

@media (max-width: 800px) {
  .textL {
    margin-right: 20px;
  }
}

@media (max-width: 400px) {
  .textL {
    margin-right: 15px;
  }
}
</style>
