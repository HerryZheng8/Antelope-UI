<demo>
普通按钮
</demo>
<template>
  <Button @click="onClick">你好</Button>
  <Button @click="onClick" theme="button">你好</Button>
  <Button @click="onClick" theme="link">你好</Button>
  <Button @click="onClick" theme="text">你好</Button>
</template>

<script lang="ts">
import Button from "../lib/Button.vue";
export default {
  components: { Button },
  setup() {
    const onClick = () => {
      console.log("hi");
    };
    return { onClick };
  },
};
</script>