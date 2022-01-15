<template>
  <article id="markdown-body" class="markdown-body" v-html="content">
  </article>
</template>
<script lang="ts">

export default {
  props:{
    content:{
      type:String,
      require:true
    }
  },
};
</script>
<style lang="scss" scoped>
.markdown-body{
  color: #1d2c40;
  background-color: transparent;
  }
</style>