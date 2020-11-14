<template>
    <!-- 自定义组件双向绑定： :value    @input -->
  <input @input="onInput" :value="value" v-bind="$attrs"/>
</template>

<script>
export default {
    inheritAttrs: false, // 设置为false避免设置到根元素上
    props: {
        value: {
            type: String,
            default: ''
        }
    },
    methods: {
        onInput(e) {
            // 派发一个input事件即可
            this.$emit('input', e.target.value);
            // 通知父级执行校验
            this.$parent.$emit('validate');
        }
    }
};
</script>

<style></style>
