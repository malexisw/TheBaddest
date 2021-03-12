<template>
  <header>
    <div class="container d-flex">
      <div class="left">
        <img src="../assets/Images/card.png" alt="Card" class="card under" />
        <img
          src="../assets/Images/card.png"
          alt="Card"
          class="card hover index1"
        />
      </div>
      <img src="../assets/kda.png" alt="KDA" class="logo" />
      <div class="right">
        <img
          src="../assets/Images/card.png"
          alt="Card"
          class="card hover index1"
        />
        <img src="../assets/Images/card.png" alt="Card" class="card under" />
      </div>
    </div>
  </header>
</template>
<script>
export default {
  name: "Header",
};
</script>

<style scoped>
header {
  position: relative;

  width: 100%;
  padding: 15px 0;
  background: var(--first-bg);
}

.container {
  align-items: center;
  justify-content: space-between;

  padding-right: 15px;
  padding-left: 15px;
  margin-right: auto;
  margin-left: auto;
}
@media (min-width: 768px) {
  .container {
    width: 750px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 970px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1170px;
  }
}

header .container img.logo {
  width: 200px;
  height: auto;
}

.card {
  position: relative;
  width: 50px;
  height: auto;
}

.left .card.under {
  transform: rotateX(-10deg) rotateY(40deg) rotateZ(-20deg) translateX(50%)
    translateY(15%);
}

.left .card.hover {
  transform: rotateX(-10deg) rotateY(-10deg) rotateZ(20deg);
}

.right .card.under {
  transform: rotateX(-10deg) rotateY(-40deg) rotateZ(20deg) translateX(-50%)
    translateY(15%);
}

.right .card.hover {
  transform: rotateX(10deg) rotateY(10deg) rotateZ(-20deg);
}

@media (max-width: 400px) {
  .card {
    width: 30px;
  }
  header .container img.logo {
    width: 150px;
    height: auto;
  }
}
</style>
