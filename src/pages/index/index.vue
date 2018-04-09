<template>
<div>
  <div id="main">
        <div class="header">
            <div class="up"></div>
            <div class="logo"></div>
        </div>
        <div class="canteen">
            <div style="height:24px;"></div>
        </div>
        <div class="loginpanel">
            <ul>
                <li>
                   <input class="input"  v-model="storeID"  type="number" placeholder="输入门店号" />
                </li>
                <li style="height:10px;">
                    &nbsp;
                </li>
                <li>
                    <input type="button" id="btnOk" value="下一步"  @click="nextStep"/>
                </li>
            </ul>
            <div style="text-align:center;">
                <span class="error">{{errorMessage}}</span>
            </div>
        </div>

        <footer class="bottom">
            苏州钱到到网络科技服务有限公司
        </footer>
    </div>
    <div id="loading">
        <img src="../../../static/imgs/loading.gif" />
    </div>
</div>
</template>

<script>
import card from "@/components/card";

export default {
  data() {
    return {
      storeID: "",
      errorMessage: ""
    };
  },
  components: {
    card
  },
  methods: {
    nextStep() {
      console.log(this.storeID);
      if (this.storeID.trim() === "") {
        this.errorMessage = "请输入门店号";
      } else {
        this.errorMessage = "";
        const url = "../logs/main";
        wx.navigateTo({ url });
      }
    }
  }
};
</script>

<style scoped>
html,
body {
  margin: 0px;
  padding: 0px;
  background-color: #eeeeef;
  font-family: 微软雅黑;
  height: 100%;
}

ul,
li {
  margin: 0px;
  padding: 0px;
  list-style-type: none;
  text-align: center;
}

.header {
  width: 100%;
  height: 153px;
  background-color: #ff6600;
  -moz-background-size: 100% 100%;
  background-size: 100% 100%;
  -moz-border-b-radius: 0px 0px 90px 90px;
  -webkit-border-radius: 0px 0px 90px 90px;
}

.header .up {
  height: 49px;
}

.logo {
  width: 105px;
  height: 41px;
  background-image: url(../../../static/imgs/logo.png);
  -moz-background-size: 100% 100%;
  background-size: 100% 100%;
  margin: 0px auto;
}

.canteen {
  height: 57px;
  text-align: center;
  font-weight: bold;
  font-size: 16px;
}

.input {
  width: 262px;
  height: 41px;
  line-height: 41px;
  background-color: white;
  -moz-border-radius: 20px;
  -webkit-border-radius: 20px;
  border: 1px solid #c8c9ca;
  font-size: 14px;
  text-align: center;
  margin: 0px auto;
}

#btnOk {
  width: 283px;
  height: 41px;
  line-height: 41px;
  background-color: #ff6600;
  -moz-border-radius: 20px;
  -webkit-border-radius: 20px;
  border: 1px solid #c8c9ca;
  font-size: 14px;
  text-align: center;
  font-weight: bold;
  color: white;
}

.loginpanel {
  display: block;
}

.bottom {
  color: #898989;
  font-size: 14px;
  height: 46px;
  line-height: 46px;
  width: 100%;
  text-align: center;
  position: absolute;
  bottom: 0px;
}

#loading {
  display: none;
}

.error {
  color: red;
  font-size: 12px;
}

input[type="date"],
input[type="button"],
input[type="text"],
select {
  -webkit-appearance: none;
  appearance: none;
}

.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}

.counter {
  display: inline-block;
  margin: 10px auto;
  padding: 5px 10px;
  color: blue;
  border: 1px solid blue;
}
</style>
