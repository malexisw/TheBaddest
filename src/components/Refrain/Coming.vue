<template>
  <div class="coming">
    <div class="left">
      <ul>
        <li>coming at <span class="grad">you</span></li>
        <li>coming at <span class="grad">you</span></li>
        <li>coming at <span class="grad">you</span></li>
        <li>coming at <span class="grad">you</span></li>
        <li class="fade un">coming at <span class="grad">you</span></li>
        <li class="fade deux">coming at <span class="grad">you</span></li>
        <li class="fade trois">coming at <span class="grad">you</span></li>
        <li class="fade quatre">coming at <span class="grad">you</span></li>
      </ul>
    </div>
    <div class="right">
      <ul>
        <li class="fade quatre">coming at <span class="grad">you</span></li>
        <li class="fade trois">coming at <span class="grad">you</span></li>
        <li class="fade deux">coming at <span class="grad">you</span></li>
        <li class="fade un">coming at <span class="grad">you</span></li>
        <li>coming at <span class="grad">you</span></li>
        <li>coming at <span class="grad">you</span></li>
        <li>coming at <span class="grad">you</span></li>
        <li>coming at <span class="grad">you</span></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Coming",
};
</script>

<style scoped>
.coming {
  display: flex;

  transform: scale(0.8);
  animation: scaleUp 0.5s forwards;
}

.left ul {
  margin-right: 20px;
}

li {
  background: -webkit-linear-gradient(#93bbec, #c3a8f9, #93bbec);
  -webkit-background-clip: text;
  -webkit-text-stroke: 2px transparent;
  color: var(--first-bg);

  font-size: 5em;
  text-transform: uppercase;
  line-height: 95px;

  white-space: nowrap;
}

.left {
  position: relative;
  top: 100px;
}

.right {
  position: relative;
  bottom: 90px;
}

.fade {
  opacity: 0;
}

.fade.un {
  animation: fadeIn 0.2s forwards;
}

.fade.deux {
  animation: fadeIn 0.2s 0.2s forwards;
}

.fade.trois {
  animation: fadeIn 0.2s 0.4s forwards;
}

.fade.quatre {
  animation: fadeIn 0.2s 0.6s forwards;
}

@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

@keyframes scaleUp {
  to {
    transform: scale(1.35);
  }
}

@media (max-width: 1100px) {
  li {
    line-height: 80px;
  }
}

@media (max-width: 800px) {
  li {
    line-height: 70px;
  }
}

@media (max-width: 400px) {
  li {
    line-height: 50px;
  }
}
</style>
