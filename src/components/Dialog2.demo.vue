<demo>
展示
</demo>
<template>
  <Button @click="showDialog">show</Button>
</template>

<script lang="ts">
import Dialog from "../lib/Dialog.vue";
import Button from "../lib/Button.vue";
import {openDialog} from "../lib/openDialog.ts";

export default {
  components: {
    Dialog, Button
  },
  setup() {
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
    return {showDialog};
  }
};
</script>