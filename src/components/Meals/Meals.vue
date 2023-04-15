<script setup>
    import Meal from "./Meal.vue";
    import {useMealsStore} from "@/store/meals"
    const meals = useMealsStore()

</script>
<template>

    <!-- 汉堡的容器 -->
    <div class="meals">
        <Meal v-for="item in meals.filterMeals" :meal="item"></Meal>
    </div>
</template>

<style scoped>
  .meals{
    height: calc(100vh - 120rem);
    padding-bottom: 150rem;
    /* background: yellowgreen; */
    overflow: auto;
  }
</style>
