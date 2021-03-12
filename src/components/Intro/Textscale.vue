<template>
  <div class="textscale">
    <p>
      We the baddest
    </p>
  </div>
</template>

<script>
export default {
  name: "Textslide",
};
</script>

<style scoped>
.textscale {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

p {
  position: relative;

  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: var(--first-bg);

  font-weight: normal;
  font-size: 8em;
  text-transform: uppercase;
  letter-spacing: 1px;

  transform: scale(10);
  letter-spacing: 150px;

  animation: scaleDown 1s forwards;
}

@keyframes scaleDown {
  15% {
    letter-spacing: 50px;
  }
  30% {
    letter-spacing: 0px;
    transform: scale(1);
  }
  40% {
    letter-spacing: 0px;
    transform: scale(1);

    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: var(--first-bg);
  }
  60% {
    letter-spacing: 0px;
    transform: scale(1);
    color: var(--first-bg);
  }
  100% {
    letter-spacing: 0px;
    transform: scale(1);
    color: var(--first-bg);

    transform: translateY(150%);
  }
}
</style>
