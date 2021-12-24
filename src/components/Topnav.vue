<template>
  <div class="topnav">
    <router-link  to="/" class="logo">
      <svg class="icon">
        <use xlink:href="#icon-list"></use>
      </svg>
    </router-link>
    <ul class="menu">
      <li>
        <router-link to="/doc">菜单1</router-link>
      </li>
      <li>菜单2</li>
    </ul>
    <svg v-if="toggleMenuButtonVisible"
        class="toggleAside" @click="toggleMenu">
      <use xlink:href="#icon-list"></use>
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
$color: #28d1c9;
.icon {
  width: 1em;
  height: 1em;
  vertical-align: -0.15em;
  fill: currentColor;
  overflow: hidden;
}

.topnav {
  color: $color;
  display: flex;
  padding: 16px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 10;
  justify-content: center;
  align-items: center;

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
    width: 24px;
    height: 24px;
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
    }
  }
}
</style>