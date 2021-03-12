<template>
  <div class="sect d-flex w100 h100">
    <div class="cut" v-if="cut">
      <p class="dark top">cut</p>
      <p class="dark bottom">cut</p>
    </div>

    <div class="razor h100 w100 abs" v-if="razor">
      <p class="dark top">
        <span class="r">r</span><span class="a">a</span><span class="z">z</span
        ><span class="o">o</span>r
      </p>
      <p class="dark bottom">
        <span class="r">r</span><span class="a">a</span><span class="z">z</span
        ><span class="o">o</span>r
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Cut",
  data: () => ({
    cut: true,
    razor: false,
  }),
  created() {
    setTimeout(() => (this.cut = false), 900);

    setTimeout(() => (this.razor = true), 800);
  },
};
</script>

<style scoped>
.sect {
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

p {
  font-size: 30em;
}

.cut p.top {
  background-image: linear-gradient(
    to bottom,
    var(--first-bg),
    var(--first-bg) 50%,
    transparent 50%
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;

  transform: translateY(47%);

  animation: slideUp 0.3s forwards;
}

.cut p.bottom {
  background-image: linear-gradient(
    to bottom,
    transparent,
    transparent 50%,
    var(--first-bg) 50%
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;

  transform: translateY(-55%);

  animation: slideDown 0.3s forwards;
}

.razor p.top {
  background-image: linear-gradient(
    to bottom,
    var(--first-bg),
    var(--first-bg) 25%,
    transparent 25%
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-text-stroke-width: 0;

  transform: translateY(70%);

  animation: razorTopAnim 0.2s forwards;
}

.razor p.bottom {
  background-image: linear-gradient(
    to bottom,
    transparent,
    transparent 70%,
    var(--first-bg) 70%
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-text-stroke-width: 0;

  transform: translateY(-75%);

  animation: razorBotAnim 0.2s forwards;
}

.cut p.bottom,
.cut p.top {
  animation-delay: 0.6s;
}

.cut,
.razor {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.cut {
  transform: scale(0.8);

  animation: scaleDown 0.2s forwards;
}

.top span.r {
  animation: swapColorRTop 0.1s 0.1s forwards;
}
.top span.a {
  animation: swapColorATop 0.1s 0.2s forwards;
}
.top span.z {
  animation: swapColorZTop 0.1s 0.3s forwards;
}
.top span.o {
  animation: swapColorOTop 0.1s 0.4s forwards;
}

.bottom span.r {
  animation: swapColorRBot 0.1s 0.1s forwards;
}
.bottom span.a {
  animation: swapColorABot 0.1s 0.2s forwards;
}
.bottom span.z {
  animation: swapColorZBot 0.1s 0.3s forwards;
}
.bottom span.o {
  animation: swapColorOBot 0.1s 0.4s forwards;
}

@keyframes swapColorRTop {
  to {
    background-image: linear-gradient(
      to bottom,
      #cac8d3,
      #cac8d3 50%,
      transparent 50%
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 1px;
  }
}

@keyframes swapColorATop {
  to {
    background-image: linear-gradient(
      to bottom,
      #c3c6cf,
      #c3c6cf 50%,
      transparent 50%
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 1px;
  }
}

@keyframes swapColorZTop {
  to {
    background-image: linear-gradient(
      to bottom,
      #c0bfc9,
      #c0bfc9 50%,
      transparent 50%
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 1px;
  }
}

@keyframes swapColorOTop {
  to {
    background-image: linear-gradient(
      to bottom,
      #b3b2bd,
      #b3b2bd 50%,
      transparent 50%
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 1px;
  }
}

@keyframes swapColorRBot {
  to {
    background-image: linear-gradient(
      to bottom,
      transparent,
      transparent 50%,
      #cac8d3 50%
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 1px;
  }
}

@keyframes swapColorABot {
  to {
    background-image: linear-gradient(
      to bottom,
      transparent,
      transparent 50%,
      #c3c6cf 50%
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 1px;
  }
}

@keyframes swapColorZBot {
  to {
    background-image: linear-gradient(
      to bottom,
      transparent,
      transparent 50%,
      #c0bfc9 50%
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 1px;
  }
}

@keyframes swapColorOBot {
  to {
    background-image: linear-gradient(
      to bottom,
      transparent,
      transparent 50%,
      #b3b2bd 50%
    );
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke-width: 1px;
  }
}

@keyframes razorTopAnim {
  to {
    background-image: linear-gradient(
      to bottom,
      var(--first-bg),
      var(--first-bg) 50%,
      transparent 50%
    );

    transform: translateY(45%);
  }
}

@keyframes razorBotAnim {
  to {
    background-image: linear-gradient(
      to bottom,
      transparent,
      transparent 50%,
      var(--first-bg) 50%
    );

    transform: translateY(-55%);
  }
}

@keyframes slideUp {
  to {
    transform: translateY(-35%);
  }
}

@keyframes slideDown {
  to {
    transform: translateY(20%);
  }
}

@keyframes scaleDown {
  to {
    transform: scale(1);
  }
}

@media (max-width: 1100px) {
  p {
    font-size: 28em;
  }
}

@media (max-width: 400px) {
  p {
    font-size: 25em;
  }
}
</style>
