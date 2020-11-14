<template>
  <div v-bind="$attrs">
    <label v-if="$attrs.label">{{$attrs.label}}</label>
    <slot></slot>
    <p v-if="error">{{error}}</p>

    <!-- <p>{{form.rules}}</p> -->
  </div>
</template>

<script>
import Schema from 'async-validator';

export default {
  inject: ['form'],
  data() {
    return {
      error: '',
    };
  },
  mounted() {
    this.$on('validate', () => {
      this.validate();
    });
  },
  methods: {
    validate() {
      // 规则
      const rules = this.form.rules[this.$attrs.prop];
      // 当前值
      const value = this.form.model[this.$attrs.prop];
      //   校验描述对象
      const desc = { [this.$attrs.prop]: rules };
      //   创建Schema实例
      const schema = new Schema(desc);
      return schema.validate({ [this.$attrs.prop]: value }, errors => {
          if(errors){
              this.error = errors[0].message;
          }else{
            //   校验通过
            this.error = "";
          }
      });
    },
  },
};
</script>

<style></style>
