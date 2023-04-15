<script setup>
    import { ref } from 'vue';
    const count = ref(0)
</script>
<template>
    <div class="counter">
        <template v-if="count > 0">
            <button class="sub" @click="count--"><i class="ri-subtract-fill"></i></button>
            <span class="count">{{ count }}</span>
        </template>
        <button class="add" @click="count++"><i class="ri-add-fill"></i></button>
    </div>
</template>

<style scoped>
    .counter{
        display: flex;
        align-items: center;
    }
    .sub,.add{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 36rem;
        height: 36rem;
        border: none;
        border-radius: 50%;
        /* font-weight: 700; */
        font-size: 36rem;
    }

    .sub{
        background-color: #fff;
        border: 1px solid #000;
    }

    .add{
        background-color: rgb(234,178,0);
    }

    .count{
        font-size: 30rem;
        margin: 0 14rem;
    }
</style>