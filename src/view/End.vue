<template>
  <div class="end">
    <div class="abs d-flex w100 h100" v-if="float">
      <Float />
    </div>
    <div class="abs d-flex w100 h100" v-if="sorry">
      <Sorry />
    </div>
    <div class="abs d-flex w100 h100" v-if="impress">
      <Impress />
    </div>
  </div>
</template>

<script>
import Float from "../components/End/Float.vue";
import Sorry from "../components/End/Sorry.vue";
import Impress from "../components/End/Impress.vue";

export default {
  name: "End",
  components: {
    Float,
    Sorry,
    Impress,
  },
  data: () => ({
    float: true,
    sorry: false,
    impress: false,
  }),
  created() {
    setTimeout(() => this.float = false, 1450)
    setTimeout(() => this.sorry = true, 1450)
    setTimeout(() => this.sorry = false, 3350)
    setTimeout(() => this.impress = true, 3250)
  },
};
</script>

<style scoped>
.end {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
