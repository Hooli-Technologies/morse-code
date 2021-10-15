<template>
  <div class="mx-8">
    <textarea v-model="code" class="rounded-full my-5 p-5"></textarea>
    <MorseCode :text="code" />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import MorseCode from "./components/MorseCode.vue";

@Options({
  components: {
    MorseCode,
  },
})
export default class App extends Vue {
  code = "Hello world";
}
</script>

<style lang="scss"></style>
