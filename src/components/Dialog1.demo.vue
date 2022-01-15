<demo>
切换
</demo>
<template>
  <Button @click="toggle">toggle</Button>
  <Dialog v-model:visible="x" :close-on-click-overlay="true" :ok="f1" :cancel="f2">
    <template v-slot:content>
      <strong>Hello world</strong>
      <div>Hi</div>
    </template>
    <template v-slot:title>
      <strong>加粗的标题</strong>
    </template>
  </Dialog>
</template>

<script lang="ts">
import Dialog from "../lib/Dialog.vue";
import Button from "../lib/Button.vue";
import {ref} from "vue";
export default {
  components: {
    Dialog, Button
  },
  setup() {
    const x = ref(false);
    const toggle = () => {
      x.value = !x.value;
    };
    const f1 = () => {
      console.log("1");
      return true;
    };
    const f2 = () => {
      console.log("2");
    };
    return {x, toggle, f1, f2};
  }
};
</script>