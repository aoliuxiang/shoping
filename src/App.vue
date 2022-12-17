<template>
  <div class="app-container">
    <h1>App 根组件</h1>
    <hr />
    <button @click="comName = 'Left'">Left</button>
    <button @click="comName = 'Right'">Right</button>
    <div class="box">
      <!-- 渲染 Left 组件和 Right 组件 -->
      <keep-alive include="myRight,myLeft">
        <component :is="comName"></component>
      </keep-alive>
    </div>
  </div>
</template>

<script>
import Left from "@/components/Left";
import Right from "@/components/Right";
export default {
  components: {
    Left,
    Right,
  },
  data() {
    return {
      comName: "Right",
    };
  },
};
</script>

<style lang="less">
.app-container {
  padding: 1px 20px 20px;
  background-color: #efefef;
}
.box {
  display: flex;
}
</style>
