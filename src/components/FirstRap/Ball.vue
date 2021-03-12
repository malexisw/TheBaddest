<template>
  <div class="ball">
    <p class="firstLine index1" v-if="first">
      i like to ball
    </p>

    <p class="secondLine index1" v-if="second">
      멈추지 않아
    </p>

    <img
      class="abs"
      src="../../assets/Images/Tiger.png"
      alt="Tiger"
      v-if="tiger"
    />
  </div>
</template>

<script>
export default {
  name: "Ball",
  data: () => ({
    first: false,
    second: false,
    tiger: false,
  }),
  created() {
    setTimeout(() => (this.first = true), 100);
    setTimeout(() => (this.first = false), 900);
    setTimeout(() => (this.second = true), 900);
    setTimeout(() => (this.tiger = true), 1600);
  },
};
</script>

<style scoped>
.ball {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  width: 100%;
  height: 100%;

  background: #3b1471;

  animation: scaleUp 1s 1.4s ease-in forwards;
}

p.firstLine {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #fff;

  transform: scale(0.9);

  animation: firstLineAnime 0.2s ease-in forwards;
}

p.secondLine {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #fff;

  font-weight: bold;

  transform: translateY(60%);

  animation: secondLineAnime 0.3s ease-in forwards;
}

img {
  width: 80%;

  opacity: 0;

  animation: fadeIn 0.7s forwards;
}

@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

@keyframes scaleUp {
  to {
    transform: scale(2) translateY(-15%);
  }
}

@keyframes secondLineAnime {
  80% {
    transform: translateY(0);

    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #fff;
  }
  100% {
    transform: translateY(0);

    color: transparent;
    background: url(../../assets/bg/bike.jpg) center no-repeat;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 0;
  }
}

@keyframes firstLineAnime {
  50% {
    transform: scale(1);

    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: #fff;
  }
  100% {
    transform: scale(1);

    color: transparent;
    background: url(../../assets/bg/bike.jpg) center no-repeat;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 0;
  }
}
</style>
