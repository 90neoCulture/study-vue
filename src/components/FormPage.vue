<template>
  <div class="hello">
    <k-form :model="form" :rules="rules" ref="loginForm">
      <k-form-item label="姓名" prop="username">
        <k-input v-model="form.username" type="text" placeholder="请输入姓名"></k-input>
        <p>{{form.username}}</p>
      </k-form-item>
      <k-form-item label="密码" prop="password">
        <k-input v-model="form.password" type="password" placeholder="请输入密码"></k-input>
        <p>{{form.password}}</p>
      </k-form-item>
      <k-form-item>
        <button @click="login">登录</button>
      </k-form-item>
    </k-form>
  </div>
</template>

<script>
import KForm from "./KForm";
import KFormItem from "./KFormItem";
import KInput from "./KInput";
import Notice from "./Notice";
export default {
  name: "HelloWorld",
  components: {
    KForm,
    KFormItem,
    KInput
  },
  data() {
    return {
      form: {
        username: '',
        password: '',
      },
      rules: {
          username: [{ required: true, message: "请输入用户名称" }],
          password: [{ required: true, message: "请输入密码" }]
        }
    }
  },
  methods: {
    login() {
      this.$refs['loginForm'].validate(valid => {
        const notice = this.$create(Notice, {
          title: "消息提醒",
          message: valid ? "请求登录！":"校验失败",
          duration: 1000
        });
        notice.show();
        // if(valid){
        //   alert('submit');
        // } else {
        //   console.log('error submit!')
        //   return false;
        // }
      })
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
