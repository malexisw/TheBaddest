<template>
  <div class="content">
    <div class="applause" v-if="applause">
      <div class="sound d-flex">
        <p class="sou grad">sou</p>
        <p class="grad">n</p>
        <p class="dof grad">d of</p>
      </div>
      <div class="ap d-flex">
        <p class="appl grad">appl</p>
        <p class="ause grad">ause</p>
      </div>
    </div>

    <div class="mean w100 h100 d-flex" v-if="mean">
      <p>you</p>
      <p>know</p>
      <p>that</p>
      <p>i</p>
      <p>mean</p>
    </div>

    <div class="everything w100 h100 d-flex" v-if="everything">
      <p class="eve">everything</p>
      <p class="sub">that i</p>
    </div>

    <div class="say w100 h100 d-flex abs" v-if="say">
        <p class="grad">say</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Applause",
  data: () => ({
    applause: true,
    mean: false,
    everything: false,
    say: false,
  }),
  created() {
    setTimeout(() => (this.applause = false), 1400);

    setTimeout(() => (this.mean = true), 1400);
    setTimeout(() => (this.mean = false), 1900);
    
    setTimeout(() => (this.everything = true), 1900);
    setTimeout(() => (this.everything = false), 2600);

    setTimeout(() => (this.say = true), 2450);
  },
};
</script>

<style scoped>
.content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  width: 100%;
  height: 100%;

  animation: slideR .15s 3s forwards;
}

/*Applause Part*/

.applause {
  animation: goUp 0.4s 1.2s forwards;
}

.sound {
  justify-content: center;
  transform: scale(2);
  animation: scaleDown 0.1s 0.4s forwards;
}

.sound p.sou {
  transform: translateX(-450%);
  animation: slide0 0.7s 0.2s forwards;
}

.sound p.dof {
  transform: translateX(450%);
  animation: slide0 0.7s 0.2s forwards;
}

.ap p {
  font-size: 14em;
  line-height: 200px;
}

p.appl {
  transform: translateX(500%);
  animation: slide0 0.55s 0.5s forwards;
}

p.ause {
  transform: translateX(-500%);
  animation: slide0 0.55s 0.5s forwards;
}

@keyframes scaleDown {
  to {
    transform: scale(1);
  }
}

@keyframes slide0 {
  to {
    transform: translate(0);
  }
}

@keyframes goUp {
  to {
    transform: translateY(-150%);
  }
}

/* Mean Part */

.mean,.everything {
  flex-direction: column;
  justify-content: center;
  align-items: center;

  background: url(../../assets/bg/bg-second.jpg) center center/cover;
}

.mean p {
  color: var(--first-bg);

  line-height: 150px;

  transform: translateY(150%);
  animation: slideScale 0.45s forwards;
}

.everything{
    animation: slideUp .25s .5s forwards;
}

.everything p{
    color: var(--first-bg);

    transform: scale(2);
    animation: scaleDown .3s forwards;
}

p.eve{
    font-size: 15em;
    line-height: 200px;
}

p.sub{
    opacity: 0;
    animation: fadeIn .15s .3s forwards;
    font-size: 8em;
    transform: translateY(100%);
}

@keyframes slideUp {
    to{
        transform: translateY(-100%);
    }
}

@keyframes fadeIn {
    to{
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes slideScale {
  50% {
    transform: translate(0) scale(1);
  }
  100% {
    transform: translate(0) scale(0);
  }
}

/* Say Part */
.say {
  flex-direction: column;
  justify-content: center;
  align-items: center;

  transform: translateY(100%);

  animation: slide0 .25s forwards;
}

.say p{
    font-size: 40em;
}

@keyframes slideR {
    to{
        transform: translateX(100%);
    }
}
</style>
