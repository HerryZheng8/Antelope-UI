<template>
  <div>
    <div class="topnavAndBanner">
      <Topnav/>
      <div class="banner">
        <h1>小羚羊UI</h1>
        <h2>一个简洁好看的 UI 框架</h2>
        <p class="actions">
          <a class="home-button" href="https://github.com">GitHub</a>
          <router-link class="home-button" to="/doc/get-started">Start</router-link>
        </p>
      </div>
    </div>
    <div class="features">
      <ul>
        <li>
          <svg>
            <use xlink:href="#icon-Vue"></use>
          </svg>
          <h3>基于 Vue 3</h3>
          <p>使用 Vue 3 Composition API 构建</p>
        </li>
        <li>
          <svg>
            <use xlink:href="#icon-file_type_typescript"></use>
          </svg>
          <h3>基于 TypeScript </h3>
          <p>源代码采用 TypeScript 书写（非严格检查）</p>
        </li>
        <li>
          <svg>
            <use xlink:href="#icon--light-bulb"></use>
          </svg>
          <h3>代码易读</h3>
          <p>每个组件的源代码都极其简洁</p>
        </li>
      </ul>
    </div>
  </div>
</template>
<script lang="ts">
import Topnav from "../components/Topnav.vue";
export default {
  components: { Topnav },
};
</script>
<style lang="scss" scoped>
$green:orange;
$border-radius:8px;
$color:orange;
.topnavAndBanner{
  clip-path: ellipse(80% 60% at 50% 40%);
  background: linear-gradient(90deg, rgba(255,255,255,1) 0%, rgba(246,195,172,1) 50%, rgba(255,138,78,0.8407738095238095) 100%);
}
.features{
  margin: 64px auto;
  width: 400px;
  @media (min-width: 800px) {
    width: 800px;
  }
  @media (min-width: 1200px) {
    width: 1200px;
  }
  >ul {
    display: flex;
    flex-wrap: wrap;
    >li {
      width: 400px;
      margin: 16px 0;
      display: grid;
      justify-content: start;
      align-content: space-between;
      grid-template-areas:
        "icon title"
        "icon text";
      grid-template-columns: 80px auto;
      grid-template-rows: 1fr auto;
      >svg {
        grid-area: icon;
        width: 64px;
        height: 64px;
      }
      >h3 {
        grid-area: title;
        font-size: 28px;
      }
      >p {
        grid-area: text
      }
    }
  }
}
.banner {
  color: $color;
  padding: 100px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  > h1,h2{
    text-shadow: 1px 2px 1px rgba(0,0,0,0.4);
  }
  > .actions{
    padding: 8px 0;
    > .home-button{
      box-shadow: 1px 2px 1px rgba(0,0,0,0.4);
    }
    a {
      margin:0 8px;
      background: $green;
      color: white;
      display: inline-block;
      padding: 8px 24px;
      border-radius: $border-radius;
      &:hover{
        text-decoration: none;
      }
    }
  }
}
</style>