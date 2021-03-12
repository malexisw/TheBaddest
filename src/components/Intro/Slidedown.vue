<template>
  <div class="slideDown">
    <p class="white top">
      Baddest
    </p>
    <p class="hidden top second">
      Baddest
    </p>
    <p class="hidden top first">
      Baddest
    </p>

    <p class="hidden bottom first">
      Baddest
    </p>
    <p class="hidden bottom second">
      Baddest
    </p>
    <p class="white bottom">
      Baddest
    </p>
  </div>
</template>

<script>
export default {
  name: "Slidedown",
};
</script>

<style scoped>
.slideDown {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.white {
  color: #fff;
}

.hidden {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: white;
}

.white.top {
  visibility: visible;
  top: -1000px;
  animation: slideDownWhite 0.3s 0.1s forwards;
}

.white.bottom {
  visibility: visible;
  bottom: -1000px;
  animation: slideUpWhite 0.3s 0.1s 1;
}

.hidden.top {
  animation: slideDown 0.3s ease-in 1;
}

.hidden.bottom {
  animation: slideUp 0.3s ease-in 1;
}

.top.first {
  top: 15%;
}

.top.second {
  top: -140px;
}

.bottom.first {
  bottom: 15%;
}

.bottom.second {
  bottom: 0%;
}

.top {
  visibility: hidden;
  position: absolute;
}

.bottom {
  visibility: hidden;
  position: absolute;
}

@keyframes slideDown {
  to {
    visibility: visible;
    top: 50%;
    transform: translateY(-50%);
  }
}

@keyframes slideUp {
  to {
    visibility: visible;
    bottom: 50%;
    transform: translateY(50%);
  }
}

@keyframes slideDownWhite {
  to {
    top: 50%;
    transform: translateY(-50%);
  }
}

@keyframes slideUpWhite {
  to {
    bottom: 50%;
    transform: translateY(50%);
  }
}
</style>
