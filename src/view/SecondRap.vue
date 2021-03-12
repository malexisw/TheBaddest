<template>
  <div class="second-rap">
    <div class="abs d-flex w100 h100" v-if="sorry">
      <Sorry />
    </div>
    <div class="abs d-flex w100 h100" v-if="bad">
      <Bad />
    </div>
    <div class="abs d-flex w100 h100" v-if="bags">
      <Bags />
    </div>
    <div class="abs d-flex w100 h100" v-if="want">
      <Want />
    </div>
    <div class="abs d-flex w100 h100" v-if="applause">
      <Applause />
    </div>

    <div class="abs d-flex w100 h100" v-if="see">
      <See />
    </div>

    <div class="abs d-flex w100 h100 slideR index1" v-if="way">
      <Way />
    </div>

    <div class="abs d-flex w100 h100" v-if="back">
      <Back />
    </div>
  </div>
</template>

<script>
import Sorry from "../components/SecondRap/Sorry.vue";
import Bad from "../components/SecondRap/Bad.vue";
import Bags from "../components/SecondRap/Bags.vue";
import Want from '../components/SecondRap/Want.vue';
import Applause from '../components/SecondRap/Applause.vue';
import See from '../components/SecondRap/See.vue';
import Way from '../components/SecondRap/Way.vue';
import Back from '../components/SecondRap/Back.vue';

export default {
  name: "SecondRap",
  components: {
    Sorry,
    Bad,
    Bags,
    Want,
    Applause,
    See,
    Way,
    Back
  },
  data: () => ({
    sorry: true,
    bad: false,
    bags: false,
    want: false,
    applause: false,
    see: false,
    way: false,
    back: false
  }),
  created() {
    setTimeout(() => this.sorry = false, 3250)

    setTimeout(() => this.bad = true, 3250)
    setTimeout(() => this.bad = false, 10140)
    
    setTimeout(() => this.bags = true, 10140)
    setTimeout(() => this.bags = false, 15550)
    
    setTimeout(() => this.want = true, 15550)
    setTimeout(() => this.want = false, 17950)

    setTimeout(() => this.applause = true, 17950)
    setTimeout(() => this.applause = false, 20950)

    setTimeout(() => this.see = true, 20950)
    setTimeout(() => this.see = false, 21950)
    
    setTimeout(() => this.way = true, 21700)
    setTimeout(() => this.way = false, 24350)
    
    setTimeout(() => this.back = true, 24250)
  },
};
</script>

<style scoped>
.second-rap {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.slideR{
  animation: slideRight .3s 2.4s forwards;
}

@keyframes slideRight {
  to{
    transform: translateX(100%);
  }
}
</style>
