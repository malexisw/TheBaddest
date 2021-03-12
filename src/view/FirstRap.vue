<template>
  <div class="first-rap">
    <div class="abs d-flex white w100 h100" v-if="transi">
      <Transi />
    </div>

    <div class="abs d-flex white w100 h100" v-if="cut">
      <Cut />
    </div>

    <div class="abs d-flex w100 h100" v-if="melt">
      <Melt />
    </div>

    <div class="abs top d-flex w100" v-if="melt">
      <SmallTextRap />
    </div>

    <div class="abs bot d-flex w100" v-if="melt">
      <SmallTextRap />
    </div>

    <div class="abs d-flex" v-if="boys">
      <Boys />
    </div>

    <div class="abs d-flex w100 h100" v-if="skull">
      <Skull />
    </div>

    <div class="abs d-flex w100 h100 index1" v-if="eyes">
      <Eyes />
    </div>

    <div class="abs d-flex w100 h100" v-if="tiger">
      <Tiger />
    </div>

    <div class="bgRed abs w100 h100 index1" v-if="bgred"></div>

    <div class="abs d-flex w100 h100" v-if="whoa">
      <Whoa />
    </div>

    <div class="abs d-flex w100 h100" v-if="ball">
      <Ball />
    </div>

    <div class="abs d-flex w100 h100" v-if="lit">
      <Lit />
    </div>

    <div class="abs d-flex w100 h100" v-if="byte">
      <Byte />
    </div>

    <div class="abs d-flex w100 h100" v-if="purple">
      <Purple />
    </div>
  </div>
</template>

<script>
import Transi from "../components/FirstRap/Transi.vue";
import Cut from "../components/FirstRap/Cut.vue";
import Melt from "../components/FirstRap/Melt.vue";
import SmallTextRap from "../components/FirstRap/smallTextRap.vue";
import Boys from "../components/FirstRap/Boys.vue";
import Skull from "../components/FirstRap/Skull.vue";
import Eyes from "../components/FirstRap/Eyes.vue";
import Tiger from "../components/FirstRap/Tiger.vue";
import Whoa from "../components/FirstRap/Whoa.vue";
import Ball from "../components/FirstRap/Ball.vue";
import Lit from "../components/FirstRap/Lit.vue";
import Byte from "../components/FirstRap/Byte.vue";
import Purple from "../components/FirstRap/Purple.vue";

export default {
  name: "FirstRap",
  components: {
    Transi,
    Cut,
    Melt,
    SmallTextRap,
    Boys,
    Skull,
    Eyes,
    Tiger,
    Whoa,
    Ball,
    Lit,
    Byte,
    Purple,
  },
  data: () => ({
    transi: true,
    cut: false,
    melt: false,
    boys: false,
    skull: false,
    eyes: false,
    tiger: false,
    bgred: false,
    whoa: false,
    ball: false,
    lit: false,
    byte: false,
    purple: false,
  }),
  created() {
    setTimeout(() => (this.transi = false), 3200);

    setTimeout(() => (this.cut = true), 3200);
    setTimeout(() => (this.cut = false), 4800);

    setTimeout(() => (this.melt = true), 4800);
    setTimeout(() => (this.melt = false), 6800);

    setTimeout(() => (this.boys = true), 6800);
    setTimeout(() => (this.boys = false), 9500);

    setTimeout(() => (this.skull = true), 9200);
    setTimeout(() => (this.skull = false), 11800);

    setTimeout(() => (this.eyes = true), 11500);
    setTimeout(() => (this.eyes = false), 13100);

    setTimeout(() => (this.tiger = true), 13100);
    setTimeout(() => (this.tiger = false), 19200);

    setTimeout(() => (this.bgred = true), 19200);
    setTimeout(() => (this.bgred = false), 19700);

    setTimeout(() => (this.whoa = true), 19700);
    setTimeout(() => (this.whoa = false), 23700);

    setTimeout(() => (this.ball = true), 23700);
    setTimeout(() => (this.ball = false), 26200);

    setTimeout(() => (this.lit = true), 26200);
    setTimeout(() => (this.lit = false), 28150);

    setTimeout(() => (this.byte = true), 28150);
    setTimeout(() => (this.byte = false), 31850);

    setTimeout(() => (this.purple = true), 31850);
    setTimeout(() => (this.purple = false), 38620);
  },
};
</script>

<style scoped>
.first-rap {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.white {
  background: #c9c8d0;
}

.top {
  top: 5%;
}

.bot {
  bottom: 5%;
}

.bgRed {
  background: #ff283f;
}
</style>
