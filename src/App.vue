<template>
  <div id="app">
    <Home />
  </div>
</template>

<script>
import Home from "./view/Home.vue";

export default {
  name: "App",
  components: {
    Home,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Anton&display=swap");

:root {
  --first-bg: #0d0c12;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  position: relative;
  height: 100%;
  overflow: hidden;
}

#app {
  overflow: hidden;
}

h1,
h2,
h3,
p {
  cursor: default;
}

p {
  position: relative;
  color: #fff;
  font-weight: normal;
  font-size: 9em;
  text-transform: uppercase;
}

p.dark {
  color: var(--first-bg);
}

ul {
  list-style: none;
}

.grad {
  background: -webkit-linear-gradient(top, #93bbec, #c3a8f9, #93bbec);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-text-stroke-width: 0;
}

.gradStroke {
  background: -webkit-linear-gradient(
    top,
    #93bbec 0%,
    #c3a8f9 50%,
    #93bbec 100%
  );
  -webkit-background-clip: text;
  -webkit-text-stroke: 2px transparent;
  color: var(--first-bg);
}

.d-flex {
  display: flex;
}

.abs {
  position: absolute;
}

.w100 {
  width: 100%;
}

.h100 {
  height: 100%;
}

.index1 {
  z-index: 1;
}

.index2 {
  z-index: 2;
}

.index3 {
  z-index: 3;
}

@media (max-width: 1100px) {
  html {
    font-size: 13px;
  }
}

@media (max-width: 800px) {
  html {
    font-size: 10px;
  }
}

@media (max-width: 400px) {
  html {
    font-size: 6px;
  }
}
</style>
