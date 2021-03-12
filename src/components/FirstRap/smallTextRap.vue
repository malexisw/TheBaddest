<template>
  <div class="small-text">
    <ul class="direction">
      <li>
        <small>baddest</small>
      </li>
      <li>
        <small>baddest</small>
      </li>
      <li>
        <small>baddest</small>
      </li>
      <li>
        <small>baddest</small>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "SmallText",
};
</script>

<style scoped>
.small-text {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
}

ul {
  display: flex;
  width: 125%;
}

ul.direction {
  animation: slide 2s forwards;
}

li {
  display: flex;
  justify-content: flex-start;
  width: 100%;
}

small {
  display: inline-block;
  color: #fff;
  text-transform: uppercase;
  font-size: 1em;
  transform: scale(2, 1);
}

@keyframes slide {
  80% {
    transform: translateX(40%);
  }
  100% {
    transform: translateX(-60%);
  }
}

</style>
