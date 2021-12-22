<template>
  <div>
    <p>dialog 的文档</p>
    <h1>示例1</h1>
    <Button @click="toggle">toggle</Button>
    <Dialog v-model:visible="x" :close-on-click-overlay="true" :ok="f1" :cancel="f2">
      <template v-slot:content>
        <strong>你好</strong>
        <div>Hi</div>
      </template>
      <template v-slot:title>
        <strong>加粗的标题</strong>
      </template>
    </Dialog>
    <h1>示例2</h1>
    <Button @click="showDialog">show</Button>
  </div>
</template>

<script lang="ts">
import Dialog from "../lib/Dialog.vue";
import Button from "../lib/Button.vue";
import {ref} from "vue";
import {openDialog} from "../lib/openDialog.ts";

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
    const showDialog = () => {
      openDialog({
        title:'标题',
        content:'你好',
        ok(){
          console.log("ok");
        },
        cancel(){
          console.log("cancel");
        }
      });
    };
    return {x, toggle, f1, f2, showDialog};
  }
};
</script>

<style lang="scss" scoped>

</style>