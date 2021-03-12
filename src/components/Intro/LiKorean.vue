<template>
  <div class="li-korean">
    <ul>
      <li>끝내주지</li>
      <li>끝내주지</li>
      <li>끝내주지</li>
      <li>끝내주지</li>
      <li>끝내주지</li>
      <li>끝내주지</li>
      <li>끝내주지</li>
      <li>끝내주지</li>
      <li>끝내주지</li>
      <li>끝내주지</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "LiKorean",
};
</script>

<style scoped>
.li-korean {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

ul {
  transform: translateY(-5%);

  animation: slideUp 5s ease forwards;
}

li {
  background: -webkit-linear-gradient(#93bbec, #96a2ee);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;

  font-weight: 600;
  font-size: 1.15em;

  margin: 15vh 0;
}

@keyframes slideUp {
  to {
    transform: translateY(-20%);
  }
}
</style>
