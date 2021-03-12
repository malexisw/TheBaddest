<template>
  <div class="small-text">
    <ul :class="direction">
      <li>
        <small>{{ smallText }}</small>
      </li>
      <li>
        <small>{{ smallText }}</small>
      </li>
      <li>
        <small>{{ smallText }}</small>
      </li>
      <li>
        <small>{{ smallText }}</small>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "SmallTextWhoa",
  props: {
    direction: String,
  },
  data: () => ({
    smallText: "whoa",
  }),
  created() {
    setTimeout(() => (this.smallText = "goat"), 1600);
    setTimeout(() => (this.smallText = "i know"), 2500);
  },
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

ul.gauche {
  animation: slideLeft 10s forwards;
}

ul.droite {
  animation: slideRight 10s forwards;
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

@keyframes slideLeft {
  to {
    transform: translateX(-50%);
  }
}

@keyframes slideRight {
  to {
    transform: translateX(50%);
  }
}
</style>
