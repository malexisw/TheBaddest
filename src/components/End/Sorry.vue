<template>
  <div class="content">
    <div class="back w100 h100 abs d-flex" v-if="sorry">
      <p class="soz">sorry</p>
    </div>
    <div class="back-not w100 h100 abs d-flex" v-if="not">
      <p class="not dark">not</p>
    </div>
    <div class="back-sor w100 h100 abs d-flex" v-if="sorry2">
      <p class="soz abs">sorry</p>
      <p class="w100 sub abs dark">
        not <span class="so">sorry</span><span class="for">for</span
        ><span class="being">being</span><span class="the">the</span
        ><span class="best">best</span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Sorry",
  data: () => ({
    sorry: true,
    not: false,
    sorry2: false,
  }),
  created() {
    setTimeout(() => (this.sorry = false), 200);

    setTimeout(() => (this.not = true), 200);
    setTimeout(() => (this.not = false), 400);

    setTimeout(() => (this.sorry2 = true), 400);
  },
};
</script>

<style scoped>
.content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  width: 100%;
  height: 100%;
}

.back,
.back-sor {
  justify-content: center;
  align-items: center;

  background: #dcd6e2;
}

.back p,
.back-sor p.soz {
  font-size: 30em;

  background-image: linear-gradient(
    to left,
    #b5eaf2,
    #8fa3ea,
    #cfaafa,
    #a6ccf0,
    #9ca1e3
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-text-stroke-width: 0;
}

.back p {
  animation: scaleHalf 0.2s forwards;
}

.back-not {
  justify-content: center;
  align-items: center;

  background: url(../../assets/bg/bg-second.jpg) center center/cover;
}

.back-not p {
  font-size: 40em;

  animation: scaleHalf 0.2s forwards;
}

.back-sor {
  text-align: center;
}

.back-sor p.soz {
  letter-spacing: -200px;
  left: 10%;

  animation: sorryAnime 0.3s forwards;
}

.back-sor p.sub {
  visibility: hidden;

  background: #dcd6e2;
  font-size: 4em;

  animation: appear 0.1s 0.3s forwards;
}

span {
  visibility: hidden;
  margin-right: 20px;
  animation: appear 0.1s forwards;
}

span.so {
  animation-delay: 0.35s;
}
span.for {
  animation-delay: 0.5s;
}
span.being {
  animation-delay: 0.6s;
}
span.the {
  animation-delay: 0.8s;
}
span.best {
  animation-delay: 0.95s;
}

@keyframes sorryAnime {
  to {
    letter-spacing: 0;
    left: 50%;
    transform: translateX(-50%);
  }
}

@keyframes appear {
  to {
    visibility: visible;
  }
}

@keyframes scaleHalf {
  to {
    transform: scale(0.6);
  }
}

@media (max-width: 1100px) {
  .back p,
  .back-sor p.soz {
    font-size: 28em;
  }
  span {
    margin-right: 20px;
  }
}

@media (max-width: 400px) {
  .back p,
  .back-sor p.soz {
    font-size: 20em;
  }
  span {
    margin-right: 5px;
  }
}
</style>
