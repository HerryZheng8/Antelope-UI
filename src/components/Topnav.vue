<template>
  <div class="topnav">
    <router-link to="/" class="logo">
      <svg class="icon">
        <use xlink:href="#icon-antelope"></use>
      </svg>
    </router-link>
    <ul class="menu">
      <li>
        <router-link to="/doc">文档</router-link>
      </li>
    </ul>
    <svg v-if="toggleMenuButtonVisible"
         class="toggleAside" @click="toggleMenu">
      <use xlink:href="#icon-list-copy"></use>
    </svg>
  </div>
</template>
<script lang="ts">
import {inject, Ref} from "vue";

export default {
  props: {
    toggleMenuButtonVisible: {
      type: Boolean,
      default: false
    }
  },
  setup() {
    const menuVisible = inject<Ref<boolean>>("menuVisible"); // get
    const toggleMenu = () => {
      menuVisible.value = !menuVisible.value;
    };
    return {toggleMenu};
  },
};
</script>
<style lang="scss" scoped>
$color: white;
.icon {
  width: 1em;
  height: 1em;
  vertical-align: -0.15em;
  fill: currentColor;
  overflow: hidden;
}

.topnav {
  display: flex;
  padding: 16px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 10;
  justify-content: center;
  align-items: center;
  color: $color;

  > .logo {
    max-width: 6em;
    margin-right: auto;

    > svg {
      width: 30px;
      height: 30px;
    }
  }

  > .menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;
    > li {
      margin: 0 1em;
    }
  }

  > .toggleAside {
    width: 26px;
    height: 26px;
    position: absolute;
    left: 16px;
    top: 50%;
    transform: translateY(-50%);
    display: none;
  }

  @media (max-width: 500px) {
    > .menu {
      display: none;
    }
    > .logo {
      margin: 0 auto;
    }
    > .toggleAside {
      display: inline-block;
      color: #1890ff;
    }
  }
}
</style>