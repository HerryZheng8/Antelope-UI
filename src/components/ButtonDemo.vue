<template>
  <div>
    <h1>Button 组件示例</h1>
    <Demo :component="Button1Demo"/>
  </div>
  <div>
    <Demo :component="Button2Demo"/>
  </div>
  <div>
    <Demo :component="Button3Demo"/>
  </div>
  <div>
    <Demo :component="Button4Demo"/>
  </div>
  <div>
    <Demo :component="Button5Demo"/>
  </div>
</template>
<script lang="ts">
import Demo from "./Demo.vue";
import Button1Demo from "./Button1.demo.vue"
import Button2Demo from "./Button2.demo.vue"
import Button3Demo from "./Button3.demo.vue"
import Button4Demo from "./Button4.demo.vue"
import Button5Demo from "./Button5.demo.vue"
export default {
  components: { Demo  },
  setup() {
    return { Button1Demo,Button2Demo,Button3Demo,Button4Demo,Button5Demo };
  },
};
</script>