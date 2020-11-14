<template>
    <!-- 自定义组件双向绑定： :value    @input -->
  <input @input="onInput" :value="value" v-bind="$attrs"/>
</template>

<script>
export default {
    inheritAttrs: false,
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
        }
    }
};
</script>

<style></style>
