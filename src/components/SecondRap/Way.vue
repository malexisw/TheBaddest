<template>
  <div class="content">
    <div class="left" v-if="way">
      <p class="dark">out of the way</p>
      <p class="dark">out of the way</p>
      <p class="dark"><span class="out">out</span> of the way</p>
      <p class="dark">out <span class="of">of</span> the way</p>
      <p class="dark">out of <span class="the">the</span> way</p>
      <p class="dark">out of the <span class="way">way</span></p>
      <p class="dark">out of the way</p>
      <p class="dark">out of the way</p>
      <p class="dark">out of the way</p>
    </div>

    <div class="slay w100 h100 d-flex" v-if="slay">
      <p class="leftSlay">slay</p>
      <p class="midSlay abs"><span class="s">s</span><span class="l">l</span><span class="a">a</span><span class="y">y</span></p>
      <p class="rightSlay">slay</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "See",
  data: () => ({
    way: true,
    slay: false,
  }),
  created() {
    setTimeout(() => (this.way = false), 1000);
    setTimeout(() => (this.slay = true), 1000);
  },
};
</script>

<style scoped>
.content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;

  width: 100%;
  height: 100%;

  background: url(../../assets/bg/bg-second.jpg) center center/cover;
  transform: translateX(-100%);

  animation: slideRight 0.3s forwards;
}

.left {
  position: relative;
  left: 5%;

  animation: scaleDown 0.2s 0.8s forwards;
}

.left p {
  font-size: 8em;
  line-height: 120px;
  word-spacing: 10px;
}

.left span {
  animation: changeStroke 0.1s forwards;
}

.left span.out {
  animation-delay: 0.3s;
}
.left span.of {
  animation-delay: 0.35s;
}
.left span.the {
  animation-delay: 0.5s;
}
.left span.way {
  animation-delay: 0.6s;
}

.slay {
  justify-content: space-between;
  align-items: center;
  background: url(../../assets/bg/bg-second.jpg) center center/cover;

  transform: scale(1.2);

  animation: scaleTo1 .15s forwards;
}

.slay p{
    font-size: 11em;
}

.slay p.leftSlay{
    margin-left: 10%;
}

.slay p.rightSlay{
    margin-right: 10%;
}

.rightSlay,.leftSlay{
    color: transparent;
    -webkit-text-stroke-width: 2px;
    -webkit-text-stroke-color: var(--first-bg);
}

.slay p.midSlay{
    left: 10%;
    
    animation: goRight .7s .5s forwards;
}

.slay p.midSlay span{
    color: transparent;
    animation: colored .1s forwards;
}

.slay p.midSlay span.s{
    animation-delay: .2s;
}
.slay p.midSlay span.l{
    animation-delay: .25s;
}
.slay p.midSlay span.a{
    animation-delay: .3s;
}
.slay p.midSlay span.y{
    animation-delay: .35s;
}

@keyframes scaleTo1 {
    to{
        transform: scale(1);
    }
}

@keyframes colored {
    to{
        color: var(--first-bg);
    }
}

@keyframes goRight {
    to{
        left: 90%;
        transform: translateX(-100%);
    }
}

@keyframes scaleDown {
  to {
    transform: scale(0.9);
  }
}

@keyframes changeStroke {
  to {
    color: transparent;
    -webkit-text-stroke-width: 2px;
    -webkit-text-stroke-color: var(--first-bg);
  }
}

@keyframes slideRight {
  to {
    transform: translateX(0);
  }
}
</style>
