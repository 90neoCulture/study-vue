<template>
  <input @input="onInput" :value="value" v-bind="$attrs"/>
</template>

<script>
export default {
    inheritAttrs: false,
    data() {
        return {
            value: ''
        }
    },
    methods: {
        onInput(e) {
            this.$emit('input', e.target.value);
        }
    }
};
</script>

<style></style>
