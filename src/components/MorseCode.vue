<template>
  <div>
    <div v-for="(word, key) in words" :key="key">
      <morse-code-converter
        v-for="(char, index) in word"
        :key="index"
        :code="representation(char)"
      />
    </div>
  </div>
</template>

<script lang="ts">
import morseCode, { MorseChar } from "./morseCode";
import MorseCodeConverter from "./MorseCodeConverter.vue";
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    text: String,
  },
  components: {
    MorseCodeConverter,
  },
})
export default class MorseCode extends Vue {
  text!: string;

  m = morseCode;

  get words(): string[][] {
    return this.text.split(" ").map((word) => word.split(""));
  }

  // get representation() {
  //   return (code: MorseChar): number[] => {
  //     return morseCode[code.toUpperCase()];
  //   };
  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
