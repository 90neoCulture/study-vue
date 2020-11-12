<template>
  <div class="hello">
    <k-form>
      <k-form-item>
        <k-input v-model="form.username" type="text" placeholder="哈哈哈"></k-input>
        <p>{{form.username}}</p>
      </k-form-item>
      <k-form-item>
        <k-input v-model="form.password" type="password"></k-input>
        <p>{{form.password}}</p>
      </k-form-item>
    </k-form>
  </div>
</template>

<script>
import KForm from "./KForm";
import KFormItem from "./KFormItem";
import KInput from "./KInput";
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
      }
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
