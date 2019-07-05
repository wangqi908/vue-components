<template>
  <div id="app">
    <!-- <router-view/> -->
    <header>头部</header>
    <main>
      <aside>
        <nav>侧边</nav>
        <nav>侧边栏</nav>
        <nav>侧边栏</nav>
        <nav>侧边栏</nav>
      </aside>
      <div class="container">
        <router-view/>
        <!--  -->
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      isShow: false
    };
  },
  methods: {
    handleShow() {
      this.isShow = !this.isShow;
    }
  }
};
</script>

<style lang='scss'>
@import url("./assets/css/reset.css");
#app {
  height: 100%;
  display: flex;
  flex-direction: column;

  header,
  aside,
  .container {
    border: 1px solid #000;
  }

  main {
    display: flex;
    flex: 1;
    overflow: auto;
  }

  aside {
    background-color: rgba(212, 255, 253, 0.651);
    overflow: auto;
    width: 90px;
  }

  .container {
    flex: 1;
    background-color: rgba(255, 226, 250, 0.514);
    overflow: auto;
  }

  nav,
  h1 {
    margin-top: 50px;
  }

  .box {
    width: 1000px;
    height: 100px;
    border: 1px solid #000;
    background-color: rgb(137, 212, 255);
  }
}
</style>
