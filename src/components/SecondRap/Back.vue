<template>
  <div class="content w100 h100">
    <div class="textBG abs">
      <div class="bg-back center d-flex">
        <p class="bg-backT abs">back</p>
        <p class="bg-better abs">better</p>
        <p class="bg-ready abs">ready</p>
      </div>
    </div>
    <div class="textFront center d-flex index1" v-if="bg">
      <div class="back dark d-flex abs">
        <p class="dark back">back</p>
        <p class="dark and1">and</p>
        <p class="dark im">i'm</p>
        <p class="dark better">better</p>
        <p class="dark and2">and</p>
        <p class="dark ready">ready</p>
        <p class="dark to">to</p>
        <p class="dark stay">stay</p>
      </div>
    </div>

    <p class="bigStay index1 grad center abs">stay</p>
  </div>
</template>

<script>
export default {
  name: "Back",
  data: () => ({
    bg: true,
  }),
  created() {
    setTimeout(() => (this.bg = false), 1000);
  },
};
</script>

<style scoped>
.content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
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

.textBG p {
  color: transparent;
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: #fff;

  font-size: 30em;
}

.textFront p {
  color: #92c6ee;
  margin-right: 20px;
}

.bg-back p {
  visibility: hidden;

  animation: appear 0.3s 1;
}

p.bg-backT {
  animation-delay: 0s;
}

p.bg-better {
  animation-delay: 0.3s;
}

p.bg-ready {
  animation-delay: 0.6s;
}

.textFront .back p {
  visibility: hidden;
  transform: translateY(-50%);

  animation: slideDownAppear 0.3s forwards;
}

.textFront .back p.and1 {
  animation-delay: 0.1s;
}
.textFront .back p.im {
  animation-delay: 0.2s;
}
.textFront .back p.better {
  animation-delay: 0.3s;
}
.textFront .back p.and2 {
  animation-delay: 0.5s;
}
.textFront .back p.ready {
  animation-delay: 0.6s;
}
.textFront .back p.to {
  animation-delay: 0.75s;
}
.textFront .back p.stay {
  animation-delay: 0.95s;
}

.bigStay {
  font-size: 35em;
  letter-spacing: 50px;
  visibility: hidden;

  animation: stayAnime 0.5s 1s forwards;
}

@keyframes stayAnime {
  0% {
    visibility: visible;
  }
  50% {
    letter-spacing: 0;
    transform: scale(1);
  }
  100% {
    letter-spacing: 0;
    transform: scale(0.5);
    visibility: visible;
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

@keyframes slideDownAppear {
  0% {
    visibility: visible;
  }
  100% {
    visibility: visible;
    transform: translateY(0);
  }
}

@media (max-width: 400px) {
  .textBG p {
    font-size: 20em;
  }
}
</style>
