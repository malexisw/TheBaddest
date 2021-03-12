<template>
  <div class="content">
    <div class="right abs d-flex">
      <div class="two-column d-flex" v-for="item in 4" :key="item">
        <div class="column-see">
          <div class="see" v-for="item in 12" :key="item">
            <p class="darkStroke">see</p>
            <p class="white">see</p>
          </div>
        </div>
        <div class="column-mee">
          <div class="mee" v-for="item in 12" :key="item">
            <p class="darkStroke">mee</p>
            <p class="white">mee</p>
          </div>
        </div>
      </div>
    </div>

    <div class="left abs"></div>
  </div>
</template>

<script>
export default {
  name: "See",
};
</script>

<style scoped>
.content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-end;

  width: 100%;
  height: 100%;

  animation: slideRight 0.3s 0.8s forwards;
}

.darkStroke {
  color: transparent;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #fff;
}

.two-column {
  animation: goRight 0.25s forwards;
}

.column-see,
.column-mee {
  display: flex;
  flex-direction: column;
  margin-right: 10px;
}

.see p,
.mee p {
  font-size: 4em;
  line-height: 80px;
}

.column-see {
  transform: translateY(-10%);
  animation: goDown 2s linear infinite;
}

.column-mee {
  transform: translateY(10%);
  animation: goUp 2s linear infinite;
}

.left {
  width: 70%;
  height: 65%;
  background: url(../../assets/bg/bg-second.jpg) center center/cover;

  left: 0;

  animation: left5 0.25s forwards;
}

@keyframes slideRight {
  to {
    transform: translateX(100%);
  }
}

@keyframes left5 {
  to {
    left: 5%;
  }
}

@keyframes goUp {
  to {
    transform: translateY(-15%);
  }
}

@keyframes goDown {
  to {
    transform: translateY(15%);
  }
}

@keyframes goRight {
  to {
    transform: translateX(150%);
  }
}

@media (max-width: 400px) {
  .see p,
  .mee p {
    font-size: 4em;
    line-height: 40px;
  }
  .column-see,
  .column-mee {
    margin-right: 0px;
  }
}
</style>
