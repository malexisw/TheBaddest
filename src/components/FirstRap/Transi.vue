<template>
  <div class="transi w100">
    <div class="first d-flex w100 h100" v-if="first">
      <div class="spit d-flex">
        <p class="sp dark">sp</p>
        <p class="it dark">it</p>
      </div>
      <div class="heat d-flex">
        <p class="he strokeBlack">he</p>
        <p class="at strokeBlack">at</p>
      </div>
    </div>

    <div class="second d-flex w100 h100" v-if="second">
      <p class="melt strokeBlack">
        melt
      </p>
      <p class="your dark">
        your
      </p>
    </div>

    <div class="third d-flex w100 h100" v-if="third">
      <p class="face dark">
        face
      </p>
      <p class="off strokeBlack">
        off
      </p>
    </div>

    <div class="fourth d-flex w100 h100 abs index1" v-if="fourth">
      <div class="textKorean index2">
        <p class="disapear dark">
          사라져
        </p>
        <p class="disapear strokeBlack">
          사라져
        </p>
      </div>
      <div class="square right"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Transi",
  data: () => ({
    first: true,
    second: false,
    third: false,
    fourth: false,
  }),
  created() {
    setTimeout(() => (this.first = false), 600);

    setTimeout(() => (this.second = true), 600);
    setTimeout(() => (this.second = false), 1200);

    setTimeout(() => (this.third = true), 1200);
    setTimeout(() => (this.third = false), 1900);

    setTimeout(() => (this.fourth = true), 1600);
  },
};
</script>

<style scoped>
.transi {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.first,
.second,
.third {
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.fourth {
  justify-content: center;
  align-items: center;
}

.first {
  transform: scale(0.5);

  animation: scaleAnim 0.6s ease-out forwards;
}

.second {
  transform: translateX(-35%);

  animation: translate20 0.6s ease-out forwards;
}

.third {
  transform: translateX(35%);

  animation: translate0 0.65s ease-out forwards;
}

p {
  font-size: 25em;
  line-height: 400px;
}

.second p,
.third p {
  font-size: 20em;
  line-height: 300px;
}

.fourth p {
  font-size: 12em;
  font-weight: bold;
  line-height: 200px;
}

.heat p {
  font-size: 27em;
}

.strokeBlack {
  color: transparent;
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: var(--first-bg);
}

.spit {
  transform: translateX(10%);
}

.sp {
  transform: translateX(-125%);
}

.it {
  transform: translateX(400%);
}

.he {
  transform: translateX(-400%);
}

.at {
  transform: translateX(325%);
}

.sp,
.it,
.he,
.at {
  animation: translate0 0.3s linear forwards;
}

.off {
  transform: translateX(30%);
  visibility: hidden;

  animation: appear 0.1s 0.08s forwards;
}

.textKorean {
  text-align: end;
  width: 30%;
  margin-bottom: 200px;

  transform: translateX(300%);

  animation: translate0 0.7s ease-out forwards;
}

.square {
  height: 20px;
  width: 45%;

  background: url("../../assets/bg/bike.jpg") center center/cover;

  transform: translateX(130%);

  animation: squareAnim 0.7s linear forwards;
}

.fourth::after {
  content: "";
  position: absolute;
  bottom: 15%;
  height: 30px;
  width: 100%;
  background: linear-gradient(to right, #6b95ae, #9697b6, #7484a6, #aec3be);
  transform: translateX(100%);

  animation: translate0 0.3s forwards;
}

@keyframes squareAnim {
  60% {
    transform: translateX(30%);
  }
  100% {
    height: 65%;
    transform: translateX(0);
  }
}

@keyframes appear {
  to {
    visibility: visible;
  }
}

@keyframes translate0 {
  to {
    transform: translateX(0);
  }
}

@keyframes translate20 {
  to {
    transform: translateX(20%);
  }
}

@keyframes scaleAnim {
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
</style>
