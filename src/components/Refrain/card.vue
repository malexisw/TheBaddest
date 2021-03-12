<template>
  <div class="card">
    <div class="container index2">
      <p class="first">hearts</p>
      <div class="d-flex second">
        <p class="in">in</p>
        <p class="twos">twos</p>
      </div>
    </div>

    <div class="cardSection">
      <img
        class="iconCard visible abs index1"
        src="../../assets/Images/card.png"
        alt=""
      />
      <img
        class="iconCard hidden abs"
        src="../../assets/Images/card.png"
        alt=""
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
};
</script>

<style scoped>
.card {
  width: 80%;
  height: 100%;
  margin: auto;

  display: flex;
  align-items: center;
  justify-content: space-between;

  animation: slideTop 0.5s linear forwards;
}

.container {
  width: 30%;
}

.cardSection {
  width: 60%;
}

.iconCard {
  transform: rotate(15deg) translateY(-50%);
  height: auto;
  width: 60%;

  top: 50%;
}

.visible {
  animation: animateCard 1s ease-out forwards;
}

.hidden {
  visibility: hidden;

  animation: appearRG 0.4s 0.7s forwards;
}

.first {
  animation: disapear 0.1s 0.6s forwards;
}

.second p {
  font-size: 10em;
}

.second {
  animation: goUp 0.6s 0.8s forwards;
}

.in {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: white;

  margin-right: 25px;
  visibility: hidden;

  animation: changeColor 0.3s 0.7s forwards;
}

.twos {
  visibility: hidden;

  animation: appear 0.1s 0.8s forwards;
}

@keyframes animateCard {
  25% {
    transform: rotateY(180deg) rotateX(15deg) translateY(-50%);
  }
  50% {
    transform: rotate(15deg) translateY(-50%);
  }
  60% {
    transform: rotate(15deg) translateY(-50%);
  }
  100% {
    transform: rotate(40deg) translateY(-50%);
  }
}

@keyframes appearRG {
  0% {
    visibility: visible;
  }
  100% {
    visibility: visible;
    transform: rotateX(-10deg) rotateY(40deg) rotateZ(-20deg)
      translate(-30%, -50%);
  }
}

@keyframes slideTop {
  0% {
    transform: translateY(100%);
  }
  100% {
    transform: translateY(0);
  }
}

@keyframes changeColor {
  50% {
    visibility: visible;
  }
  100% {
    color: #fff;
    visibility: visible;
  }
}

@keyframes goUp {
  to {
    transform: translateY(-30%);
  }
}

@keyframes disapear {
  to {
    visibility: hidden;
  }
}

@keyframes appear {
  to {
    visibility: visible;
  }
}

@media (max-width: 1100px) {
  .iconCard {
    width: 40%;
  }
}

@media (max-width: 800px) {
  .iconCard {
    width: 40%;
  }
}

</style>
