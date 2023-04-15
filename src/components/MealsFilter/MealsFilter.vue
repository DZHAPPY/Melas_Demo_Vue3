<script setup>
    import { useMealsStore } from '../../store/meals';
    const meals = useMealsStore()
</script>
<template>
    <div class="filter">
        <div class="filter-inner">
            <i class="ri-search-line"></i>
            <input v-model="meals.$state.keyWord" type="text" class="filter-input" placeholder="请输入相关商品">
        </div>
    </div>
</template>

<style scoped>
    .filter{
        padding: 20rem 40rem;
        border-bottom: 1px solid #e6e6e6;
    }

    .filter-inner{
        display: flex;
        position: relative;
        align-items: center;
        height: 80rem;
        background-color: #fff;
    }
    .filter-inner i{
        position: absolute;
        color: rgb(184,184,184);
        font-size: 36rem;
        left: 20rem;
    }
    .filter-input{
        width: 100%;
        border: none;
        height: 80rem;
        border-radius: 40rem;
        background-color: rgb(242,242,242);
        outline: none;
        padding: 0 40rem 0 80rem;
    }
</style>