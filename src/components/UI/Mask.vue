<script setup>

    const props = defineProps(['isShow'])
</script>
<template>
    <div class="mask" v-show="props.isShow">
        <slot></slot>
    </div>
</template>

<style scoped>
    .mask{
        position: fixed;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background-color: rgba(0,0,0,0.3);
        z-index: 10;
    }
</style>