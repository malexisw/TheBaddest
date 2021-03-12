<template>
  <div class="logoSlide2">
    <ul>
      <li><img src="../../assets/original/logo4.png" alt="" /></li>
      <li><img src="../../assets/original/logo4.png" alt="" /></li>
      <li><img src="../../assets/original/logo4.png" alt="" /></li>
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
  bottom: 80px;

  animation: slideBottom 1s ease-out forwards;
}

li {
  width: 400px;
}

img {
  width: 100%;
}

@keyframes slideBottom {
  to {
    bottom: -80px;
  }
}
</style>
