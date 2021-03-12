<template>
  <div class="sorry">
    <div class="bgSlide w100 h100" v-if="bg"></div>
    <h1 class="slash abs">/</h1>

    <h1 class="sorryText grad" v-if="sor">sorry</h1>
    <div class="cut abs d-flex" v-if="sor">
      <p>
        <span class="for">for</span><span class="the">the</span>
        <span class="bad">bad</span><span class="news">news</span>
        <span class="sorr">sorry</span><span class="i">i'm</span>
        <span class="so">so</span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Sorry",
  data: () => ({
    bg: true,
    sor: false,
  }),
  created() {
    setTimeout(() => (this.bg = false), 300);
    setTimeout(() => (this.sor = true), 600);
  },
};
</script>

<style scoped>
.sorry {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  width: 100%;
  height: 100%;
}

.bgSlide {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  background: #f3efec;
  transform: translateY(100%);
  animation: slideUp 0.2s linear forwards;
}

h1.slash {
  color: transparent;
  background: url(../../assets/bg/bike.jpg) center no-repeat;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-text-stroke-width: 0;

  font-size: 20em;
  font-weight: 100;

  transform: translateX(0) scale(2);
  visibility: hidden;

  animation: slashAnime 0.3s 0.1s linear forwards;
}

h1.sorryText {
  text-transform: uppercase;
  font-size: 25em;
  font-weight: 100;
  transform: scale(1, 0);

  animation: scaleUp 0.5s linear forwards;
}

.cut {
  height: 100px;
  width: 100%;
  background: var(--first-bg);
}

.cut p {
  width: 100%;
  text-align: center;
  font-size: 4em;
}

.cut p span {
  margin-right: 20px;
  visibility: hidden;
  animation: appear 0.1s forwards;
}

.cut p span.for {
  animation-delay: 0.7s;
}

.cut p span.the {
  animation-delay: 0.85s;
}

.cut p span.bad {
  animation-delay: 1s;
}

.cut p span.news {
  animation-delay: 1.3s;
}

.cut p span.sorr {
  animation-delay: 1.7s;
}

.cut p span.i {
  animation-delay: 2.2s;
}

.cut p span.so {
  animation-delay: 2.35s;
}

@keyframes scaleUp {
  to {
    transform: scale(1, 1);
  }
}

@keyframes appear {
  to {
    visibility: visible;
  }
}

@keyframes slashAnime {
  0% {
    visibility: visible;
  }
  100% {
    transform: translateX(-500%) scale(0);
    visibility: visible;
  }
}

@keyframes slideUp {
  to {
    transform: translateY(0);
  }
}

@media (max-width: 1100px) {
  .cut {
    height: 80px;
  }
  .cut p span {
    margin-right: 20px;
  }
}

@media (max-width: 800px) {
  .cut {
    height: 60px;
  }
  .cut p span {
    margin-right: 15px;
  }
}

@media (max-width: 400px) {
  .cut {
    height: 40px;
  }
  .cut p span {
    margin-right: 5px;
  }
}
</style>
