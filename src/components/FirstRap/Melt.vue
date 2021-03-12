<template>
  <div class="d-flex w100 h100 scale">
    <div class="melt w100 " v-if="melt">
      <p class="top">murdermudermurder</p>
      <p class="mid">murder<span>murder</span>murder</p>
      <p class="bottom">murdermudermurder</p>
    </div>
    <div class="blazer w100" v-if="blazer">
      <p class="top">blazerblazerblazer</p>
      <p class="mid">blazer<span>blazer</span>blazer</p>
      <p class="bottom">blazerblazerblazer</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Melt",
  data: () => ({
    melt: true,
    blazer: false,
  }),
  created() {
    setTimeout(() => (this.melt = false), 1000);

    setTimeout(() => (this.blazer = true), 1000);
  },
};
</script>

<style scoped>
.scale {
  animation: scaleDown 0.1s 0.5s forwards;
}

.melt,
.blazer {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}

.melt {
  transform: translateX(50%);

  animation: translate0 1s linear forwards;
}

.blazer {
  transform: translateX(30%);

  animation: slideLeft 1s ease-in forwards;
}

p {
  font-size: 35em;
  line-height: 525px;
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: white;
}

p span {
  color: white;
}

@keyframes scaleDown {
  to {
    transform: scale(0.8);
  }
}

@keyframes translate0 {
  to {
    transform: translateX(0);
  }
}

@keyframes slideLeft {
  to {
    transform: translateX(-160%);
  }
}

@media (max-width: 1100px) {
  p {
    font-size: 20em;
    line-height: 240px;
  }
}

@media (max-width: 800px) {
  p {
    font-size: 24em;
    line-height: 220px;
  }
}

@media (max-width: 400px) {
  p {
    font-size: 45em;
    line-height: 240px;
  }
}
</style>
