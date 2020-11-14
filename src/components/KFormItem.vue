<template>
    <div v-bind="$attrs">
        <label v-if="$attrs.label">{{$attrs.label}}</label>
        <slot></slot>
        <p v-if="error">{{error}}</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
            error: ''
        }
    },
};
</script>

<style></style>
