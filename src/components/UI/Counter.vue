<script setup>
    import { useMealsStore } from '../../store/meals';
    const meals = useMealsStore()
    const props = defineProps(['meal'])
</script>
<template>
    <div class="counter">
        <template v-if="props.meal.count > 0">
            <button class="sub" @click="meals.subMealFromCart(meal)"><i class="ri-subtract-fill"></i></button>
            <span class="count">{{ props.meal.count }}</span>
        </template>
        <button class="add" @click="meals.addMealToCart(meal)"><i class="ri-add-fill"></i></button>
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