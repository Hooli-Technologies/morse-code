<template>
  <div>
    <span
      v-for="(symbol, i) in code"
      :key="i"
      :class="`morse-${symbol}`"
    ></span>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    code: String,
  },
})
export default class MorseCodeConverter extends Vue {
  code!: number[];
}
</script>
<style>
.morse-0 {
  background: black;
  width: 20px;
  display: inline-block;
  height: 20px;
  margin: 10px;
}

.morse-1 {
  background: black;
  width: 60px;
  display: inline-block;
  height: 20px;
  margin: 10px;
}
</style>
