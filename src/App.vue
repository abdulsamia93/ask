<template>
  <div class="all">
    <header>
      <div class="logo">أسئلة وأجوبة</div>

      <router-link class="btn-menu" to="/">أحدث الأسئلة</router-link>
      <router-link class="btn-menu" to="/about">الأكثر إجابة</router-link>
      <router-link class="btn-menu" to="/about">الأكثر نقاط</router-link>
      <router-link class="btn-menu" v-show="isuser" to="/about">طرح سؤال</router-link>

      <div class="user-box">
        <div class="user" v-show="isuser">
          <router-link class="acount" to="/">حسابي</router-link>
          <router-link class="logout" to="/">خروج</router-link>
        </div>
        <div class="no-user" v-show="isuser==false">
          <router-link class="new" to="/">تسجيل</router-link>
          <router-link class="login" to="/">دخول</router-link>
        </div>
      </div>
    </header>

    <content>
      <router-view />
    </content>
  </div>
</template>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Cairo");
body {
  margin: 0px;
  padding: 0px;
  background: #e3eaf0;
  font-family: "cairo";
}
.all {
  float: right;
  direction: rtl;
  background: #fff;
  width: 1000px;
  margin: 0px calc(50% - 500px);
}
header {
  float: right;
  width: 100%;
  height: 70px;
  background: #fff;
  border-bottom: 1px solid #333;
  .logo {
    float: right;
    line-height: 70px;
    color: #34495e;
    font-size: 30px;
    font-weight: bold;
    width: 200px;
    abackground: #aaa;
    text-align: center;
    margin-left: 15px;
    margin-right: 15px;
  }
  .btn-menu {
    float: right;
    margin-right: 15px;
    margin-left: 15px;
    margin-top: 20px;
    margin-bottom: 20px;
    line-height: 30px;
    abackground-color: #e3eaf0;
    color: #34495e;
    font-size: 18px;
    text-decoration: none;
  }
  .btn-menu:hover {
    color: #e67e22;
    border-bottom: 1px solid #e67e22;
  }
  .user-box {
    float: left;
    height: 60px;
    margin: 5px;
    abackground-color: #e67e22;
    width: 180px;
  }
  .user {
    float: left;
    awidth: 100%;
    height: 50px;
    line-height: 50px;
    margin: 5px 0px;
    margin-left: 10px;
    .acount {
      float: right;
      font-size: 20px;
      color: #e67e22;
      text-decoration: none;
    }
    .logout {
      float: right;
      font-size: 14px;
      color: #666;
      margin-right: 6px;
      text-decoration: none;
    }
  }
  .no-user {
    float: left;
    awidth: 100%;
    height: 50px;
    line-height: 50px;
    margin: 5px 0px;
    margin-left: 10px;
    .new {
      float: right;
      padding: 0px 6px;
      background: #e67e22;
      color: #fff;
      text-decoration: none;
    }
    .login {
      float: right;
      margin-right: 10px;
      padding: 0px 6px;
      background: #34495e;
      color: #fff;
      text-decoration: none;
    }
  }
}
content {
  padding: 10px;
  width: calc(100% - 20px);
}
</style>




<script>
export default {
  data: function() {
    return {
      isuser: false
    };
  }
};
</script>