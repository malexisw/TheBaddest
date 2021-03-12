<template>
  <div class="logoSlide2">
    <ul>
      <li><img src="../../assets/original/logo2.png" alt="" /></li>
      <li><img src="../../assets/original/logo2.png" alt="" /></li>
      <li><img src="../../assets/original/logo2.png" alt="" /></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "LogoSlide2",
};
</script>

<style scoped>
.logoSlide2 {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

ul {
  position: relative;
  bottom: 120px;

  animation: slideBottom 1s ease-out forwards;
}

li {
  width: 400px;
}

img {
  width: 100%;
}

@keyframes slideBottom {
  50% {
    bottom: 0px;
  }
  100% {
    bottom: -100px;
  }
}
</style>
