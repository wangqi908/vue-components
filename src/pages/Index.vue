<template>
  <div class="index">
    <button @click="handleShow">按钮</button>
    <p>
      {{isShow}}
    </p>
    <h1>内容</h1>
    <Drawer :visible.sync="isShow" @before-close='handleClose'>
      <p>受理工程</p>
      <p>受理工程</p>
      <p>受理工程</p>
      <p>受理工程</p>
      <p>受理工程</p>
      <p>受理工程</p>
      <p>受理工程</p>
      <p>受理工程</p>
      <p>受理工程</p>
      <p>受理工程</p>
      <p>受理工程</p>
      <p>受理工程</p>
      <div class="bottomBox">
        底部盒子
      </div>
    </Drawer>
    <button @click="shop">购物车</button>
    <button @click="login">登录</button>
  </div>
</template>

<script>
import Drawer from "@/components/Drawer";
export default {
  components: {
    Drawer
  },
  data() {
    return {
      isShow: false
    };
  },
  methods: {
    handleShow() {
      this.isShow = !this.isShow;
    },
    handleClose() {
      console.log("关闭");
    },
    shop() {
      this.$router.push('./shop')
    },
    login() {
      this.$router.push('./login')
    }
  }
};
</script>

<style lang='scss'>
.index {
  .drawer {
    width: 200px;
    p {
      border: 1px solid #000;
      padding: 110px 0;
    }
  }
  .bottomBox {
    border: 1px solid #000;
    position: absolute;
    bottom: 0;
    width: 100%;
    background-color: rgb(147, 196, 224);
    box-sizing: border-box;
  }
}
</style>
