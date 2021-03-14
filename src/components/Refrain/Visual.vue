<template>
  <div class="visual">
    <div class="rectangle abs"></div>
    <div class="container first d-flex index1" v-if="!perso">
      <img class="akali" src="../../assets/Images/Akali.jpg" alt="Akali" />
      <img class="eve" src="../../assets/Images/Eve.jpg" alt="Eve" />
      <img class="ahri" src="../../assets/Images/Ahri.jpg" alt="Ahri" />
      <img class="kai" src="../../assets/Images/Kai.jpg" alt="Kai" />
    </div>
    <div class="container d-flex second index1" v-if="perso">
      <img
        class="allPerso"
        src="../../assets/Images/Perso_BG.jpg"
        alt="AllPerso"
      />
    </div>
    <div class="bottom d-flex">
      <p class="spaceL">
        <span class="that">that's</span> <span class="what">what</span> the
      </p>
      <div class="subText d-flex">
        <div class="d-flex baddest">
          <div class="expand abs"></div>
          <p class="bad">bad</p>
          <p class="dest">dest</p>
        </div>
        <p class="do">do</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Visual",
  data: () => ({
    perso: false,
  }),
  created() {
    setTimeout(() => (this.perso = true), 1650);
  },
};
</script>

<style scoped>
.visual {
  width: 100%;
  height: 100%;
}
.rectangle {
  width: 250px;
  height: 500px;

  background: url("../../assets/bg/bg-second.jpg") center center/cover;

  left: 10%;
  top: 100%;

  animation: slideUp 0.5s ease-out forwards;
}

.container {
  position: relative;

  justify-content: center;
  height: 50%;
  width: 80%;
  margin: auto;
}

.container.first {
  align-items: flex-end;
  animation: fadeRight 0.2s 1.6s forwards;
}

.container.second {
  opacity: 0;

  width: 80%;
  justify-content: center;

  animation: fadeIn 0.2s forwards;
}

.container.second img {
  height: auto;
  max-width: 100%;
  object-fit: cover;
}

.container.first img {
  margin-right: 25px;

  height: auto;
  max-width: 25%;
}

.bottom {
  flex-direction: column;

  width: 100%;
  text-align: center;

  margin-top: 50px;
  justify-content: flex-start;
  align-items: flex-start;

  line-height: 130px;

  transform: translateY(100%);

  animation: goUp 0.9s 0.25s forwards;
}

.spaceL .that {
  margin-right: 400px;

  animation: marginChangeThat 0.3s 0.25s forwards;
}

.spaceL .what {
  animation: marginChangeWhat 0.6s 0.25s forwards;
}

.spaceL {
  width: 80%;
  margin: 0 auto;
  text-align: start;
  animation: changeColor 0.1s 1.6s forwards;
}

.subText {
  position: relative;
  width: 75%;

  justify-content: flex-end;
  align-items: center;
  height: 122px;
  transform: translateY(25%);
}

.expand {
  visibility: hidden;
  height: 100%;
  transform: translateX(-90%);

  background: -webkit-linear-gradient(top, #93bbec, #c3a8f9, #93bbec);

  animation: expandBaddest 0.3s 1.5s forwards;
}

.baddest {
  margin-right: 50px;

  align-items: center;
}

.bad,
.dest,
.do {
  opacity: 0;
  transform: translateY(100%);

  animation: fadeInBad 0.7s 0.85s forwards;
}

.dest {
  animation: fadeInDest 0.5s 1s forwards;
}

.do {
  animation: fadeInDo 0.3s 1.25s forwards;
}

.akali,
.eve,
.ahri,
.kai {
  transform: translateY(-150%);
  animation: slideDown 0.8s 0.2s forwards;
}

.eve {
  animation-delay: 0.4s;
}

.ahri {
  animation-delay: 0.6s;
}

.kai {
  animation-delay: 0.8s;
}

@keyframes fadeRight {
  to {
    transform: translateX(20%);
    opacity: 0;
  }
}

@keyframes slideDown {
  to {
    transform: translateY(0);
  }
}

@keyframes expandBaddest {
  0% {
    visibility: visible;
    width: 0%;
  }
  100% {
    visibility: visible;
    transform: translateX(-98%);
    width: 60%;
  }
}

@keyframes changeColor {
  to {
    color: transparent;
    -webkit-text-stroke-width: 0.5px;
    -webkit-text-stroke-color: white;
  }
}

@keyframes fadeInDo {
  80% {
    transform: translateY(0);
    opacity: 1;
  }
  99% {
    transform: translateY(0);
    opacity: 1;

    background: transparent;
    -webkit-background-clip: text;
    -webkit-text-fill-color: #fff;
    -webkit-text-stroke-width: 0;
  }
  100% {
    transform: translateY(0);
    opacity: 1;

    background: -webkit-linear-gradient(top, #93bbec, #c3a8f9, #93bbec);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 0;
  }
}

@keyframes fadeInDest {
  70% {
    transform: translateY(0);
    opacity: 1;
  }
  99% {
    transform: translateY(0);
    opacity: 1;

    background: transparent;
    -webkit-background-clip: text;
    -webkit-text-fill-color: #fff;
    -webkit-text-stroke-width: 0;
  }
  100% {
    transform: translateY(0);
    opacity: 1;

    background: -webkit-linear-gradient(top, #93bbec, #c3a8f9, #93bbec);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 0;
  }
}

@keyframes fadeInBad {
  50% {
    transform: translateY(0);
    opacity: 1;
  }
  90% {
    transform: translateY(0);
    opacity: 1;

    background: transparent;
    -webkit-background-clip: text;
    -webkit-text-fill-color: #fff;
    -webkit-text-stroke-width: 0;
  }
  100% {
    transform: translateY(0);
    opacity: 1;

    background: -webkit-linear-gradient(top, #93bbec, #c3a8f9, #93bbec);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 0;
  }
}

@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

@keyframes marginChangeThat {
  to {
    margin-right: 0;
  }
}

@keyframes marginChangeWhat {
  50% {
    margin-right: 400px;
  }
  100% {
    margin-right: 0;
  }
}

@keyframes goUp {
  to {
    transform: translateY(0);
  }
}

@keyframes slideUp {
  to {
    top: 0;
  }
}

@media (max-width: 1100px) {
  .rectangle {
    width: 200px;
    height: 400px;
  }
  .bottom {
    margin-top: 40px;

    line-height: 120px;

    transform: translateY(100%);
  }
  .baddest {
    margin-right: 30px;
  }
  .subText {
    height: 100px;
  }
}

@media (max-width: 800px) {
  .rectangle {
    width: 150px;
    height: 400px;
  }
  .bottom {
    margin-top: 30px;

    line-height: 100px;

    transform: translateY(100%);
  }
  .baddest {
    margin-right: 20px;
  }
  .subText {
    height: 80px;
  }
}

@media (max-width: 400px) {
  .rectangle {
    width: 100px;
    height: 250px;
  }
  .container.first img {
    margin-right: 15px;
  }
  .bottom {
    margin-top: 20px;

    line-height: 60px;

    transform: translateY(100%);
  }
  p.spaceL {
    font-size: 7.5em;
  }
  .baddest {
    margin-right: 10px;
  }
  .subText {
    height: 45px;
  }
}
</style>
