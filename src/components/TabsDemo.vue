<template>
  <h1>Tabs 组件示例</h1>
  <div>
    <Demo :component="TabsDemo"/>
  </div>
</template>

<script lang="ts">
import Tabs from '../lib/Tabs.vue'
import Tab from '../lib/Tab.vue'
import {ref} from "vue";
import Demo from "./Demo.vue"
import TabsDemo from "./Tabs.demo.vue"

export default {
components:{
  Tabs,Tab,Demo
},
  setup(){
  const x = ref('导航1')
    return{x,TabsDemo}
  }
};
</script>
