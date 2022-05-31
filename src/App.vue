<template>
  <div class="container">
    <nut-navbar
      title="首页"
      :left-show="false"
      :style="headerStyle"
      :fixed="true"
    ></nut-navbar>
    <div class="body">
      <nut-button type="primary" @click="btnclick">主要按钮</nut-button>
      <nut-button :style="selfstyle" type="primary">信息</nut-button>
      <nut-button type="default">默认按钮</nut-button>
      <nut-button plain type="primary" :class="[myButton]">朴素按钮</nut-button>
      <router-view />
    </div>
  </div>
  <div class="botttom-tabbar">
    <nut-tabbar
      @tab-switch="tabSwitch"
      :bottom="true"
      :safeAreaInsetBottom="true"
    >
      <nut-tabbar-item tab-title="首页" icon="home"></nut-tabbar-item>
      <nut-tabbar-item tab-title="会员" img="http://img20.360buyimg.com/uba/jfs/t1/20004/20/1045/3620/5c0f3d61Eaaec1670/9e59db63983b7b9f.jpg"
      activeImg="http://img14.360buyimg.com/uba/jfs/t1/23967/14/1072/6714/5c0f3d61E0ad8991e/8f741953f6e38f15.jpg">
      </nut-tabbar-item>
      <nut-tabbar-item tab-title="购物车" icon="cart"></nut-tabbar-item>
      <nut-tabbar-item tab-title="搜索" icon="search"></nut-tabbar-item>
    </nut-tabbar>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selfstyle: {
        color: "white",
        width: "80px",
        height: "30px",
        backgroundColor: "blue",
        fontSize: "18px",
        paddingLeft: "0px",
        paddingRight: "0px",
      },
      headerStyle: {
        color: "red",
        fontSize: 20 + "px",
      },
    };
  },
  methods: {
    btnclick() {
      console.log("主要按钮--------------------点击事件");
    },
    tabSwitch(item, index) {
      console.log("底部tab切换---");
      console.log(item, index);
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.nut-button {
  width: 5px;
  height: 5px;
  border-radius: 10;
  background-color: red;
}
.myButton {
  font-size: 30px;
  background-color: orange;
  border-radius: 30px;
  color: #42b983;
}

.container {
  //头部
  .nut-navbar__title .title {
    color: red;
    font-size: 30px;
  }
  // 内容
  .body {
    margin-top: 44px;
  }
  // 底部tab
  .botttom-tabbar {
    height: 300;
    background-color: rgb(255, 0, 0);
    widows: 300;
  }
}
</style>
