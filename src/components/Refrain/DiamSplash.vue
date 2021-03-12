<template>
  <div class="diam-splash">
    <div class="diamonds">
      <p class="diams">diamonds</p>
      <div class="groupFall">
        <div class="fall un"></div>
        <div class="fall deux"></div>
        <div class="fall trois"></div>
        <div class="fall quatre"></div>
      </div>
    </div>
    <div class="space h100"></div>

    <div class="splash">
      <p class="spla">splash</p>
      <div class="subGroup abs">
        <p class="first index3">splash</p>
        <p class="second index2">splash</p>
        <p class="third index1">splash</p>
        <p class="fourth">splash</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DiamSplash",
};
</script>

<style scoped>
.diam-splash {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 300%;

  transform: translateY(4%);

  animation: goDown 0.8s 1s ease-out forwards;
}

.diamonds,
.splash {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
}

.groupFall {
  position: relative;
  display: flex;
  justify-content: center;
}

p {
  font-size: 15em;
}

.diams {
  color: transparent;
  -webkit-text-stroke-width: 0.5px;
  -webkit-text-stroke-color: white;

  letter-spacing: 50px;
  line-height: 170px;

  animation: animateDiamsText 0.3s 0.4s forwards;
}

.spla {
  color: transparent;
  -webkit-text-stroke-width: 0.5px;
  -webkit-text-stroke-color: white;

  letter-spacing: 10px;

  animation: colored 0.3s 1.95s linear forwards;

  z-index: 10;
}

.subGroup p {
  color: var(--first-bg);
  -webkit-text-stroke-width: 0.5px;
  -webkit-text-stroke-color: white;

  line-height: 0px;
  letter-spacing: 10px;

  transform: translateY(0px);

  animation: splashDown 0.3s 2s forwards;
}

.fall {
  position: relative;
  height: 200px;
  background: #fff;

  visibility: hidden;

  animation: leak 1.4s 0.7s ease-out forwards;
}

.fall.un {
  right: 260px;
  width: 42px;
}

.fall.deux {
  width: 40px;
  right: 130px;
}

.fall.trois {
  width: 40px;
  right: 46px;

  animation-delay: 0.75s;
}

.fall.quatre {
  width: 42px;
  left: 87px;
}

@keyframes splashDown {
  to {
    line-height: 100px;
    transform: translateY(250px);
  }
}

@keyframes colored {
  20% {
    background-image: linear-gradient(
      to bottom,
      #bfd6f5,
      #bfd6f5 30%,
      transparent 30%,
      transparent 85%,
      transparent 85%
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
  50% {
    background-image: linear-gradient(
      to bottom,
      #bfd6f5,
      #bfd6f5,
      #e0f1f8,
      #e0f1f8 60%,
      transparent 60%
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
  100% {
    background-image: linear-gradient(to bottom, #bfd6f5, #e0f1f8, #cad1fb);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
}

@keyframes goDown {
  to {
    transform: translateY(-68%);
  }
}

@keyframes leak {
  0% {
    visibility: visible;
  }
  25% {
    height: 80vh;
  }
  50% {
    height: 80vh;
    transform: translateY(0%);
    background: #fff;
  }
  70% {
    height: 200px;
    background: rgb(84, 159, 209);
  }
  100% {
    background: rgb(84, 159, 209);
    transform: translateY(920%);
    visibility: hidden;
  }
}

@keyframes animateDiamsText {
  to {
    letter-spacing: 0px;
    color: #fff;
  }
}

@media (max-width: 1100px) {
  @keyframes leak {
    0% {
      visibility: visible;
    }
    25% {
      height: 80vh;
    }
    50% {
      height: 80vh;
      transform: translateY(0%);
      background: #fff;
    }
    70% {
      height: 150px;
      background: rgb(84, 159, 209);
    }
    100% {
      background: rgb(84, 159, 209);
      transform: translateY(700%);
      visibility: hidden;
    }
  }
}

@media (max-width: 800px) {
  .fall{
    height: 150px;
    transform: translateY(-10%);
  }

  .fall.un {
    right: 163px;
    width: 25px;
  }

  .fall.deux {
    width: 25px;
    right: 85px;
  }

  .fall.trois {
    width: 23px;
    right: 27px;

    animation-delay: 0.75s;
  }

  .fall.quatre {
    width: 25px;
    left: 55px;
  }
  @keyframes leak {
    0% {
      visibility: visible;
    }
    25% {
      height: 80vh;
    }
    50% {
      height: 80vh;
      transform: translateY(0%);
      background: #fff;
    }
    70% {
      height: 150px;
      background: rgb(84, 159, 209);
    }
    100% {
      background: rgb(84, 159, 209);
      transform: translateY(1250%);
      visibility: hidden;
    }
  }
}

@media (max-width: 400px) {
  .fall{
    height: 100px;
    transform: translateY(-50%);
  }
  .fall.un {
    right: 98px;
    width: 15px;
  }

  .fall.deux {
    width: 15px;
    right: 50px;
  }

  .fall.trois {
    width: 13px;
    right: 17px;

    animation-delay: 0.75s;
  }

  .fall.quatre {
    width: 15px;
    left: 35px;
  }
  @keyframes leak {
    0% {
      visibility: visible;
    }
    25% {
      height: 80vh;
    }
    50% {
      height: 80vh;
      transform: translateY(0%);
      background: #fff;
    }
    70% {
      height: 150px;
      background: rgb(84, 159, 209);
    }
    100% {
      background: rgb(84, 159, 209);
      transform: translateY(1500%);
      visibility: hidden;
    }
  }
}
</style>
