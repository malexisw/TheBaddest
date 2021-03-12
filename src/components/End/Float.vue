<template>
  <div class="content">
    <div class="cadre"></div>
  </div>
</template>

<script>
export default {
  name: "Float",
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

.cadre {
  width: 100%;
  height: 100%;

  background: url(../../assets/bg/bg-second.jpg) center center/cover;

  animation: scaleDown 1.5s ease-in-out forwards;
}

@keyframes scaleDown {
  to {
    transform: scale(0.7);
  }
}
</style>
