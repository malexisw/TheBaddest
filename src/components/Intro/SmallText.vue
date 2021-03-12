<template>
  <div class="small-text">
    <ul :class="direction">
      <li>
        <small>the baddest</small>
      </li>
      <li>
        <small>the baddest</small>
      </li>
      <li>
        <small>the baddest</small>
      </li>
      <li>
        <small>the baddest</small>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "SmallText",
  props: {
    direction: String,
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
  animation: slideLeft 5s forwards;
}

ul.droite {
  animation: slideRight 5s forwards;
}

li {
  display: flex;
  justify-content: flex-end;
  width: 100%;
}

small {
  display: inline-block;
  color: #8363f2;
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
