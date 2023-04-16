<script setup>
    import Mask from "../UI/Mask.vue"
    import cartBag from "../../assets/bag.png"
    import { useMealsStore } from "../../store/meals";
    import { ref } from "vue";
    const Meals = useMealsStore()
    const showDetails = ref(false)
</script>
<template>
    <Mask :is-show="showDetails" @click="showDetails = !showDetails">
        
    </Mask>
    <div class="cart-bar" @click="Meals.totalCount > 0 ? showDetails = true:0">
        <div class="cart-bag">
            <img :src="cartBag" alt="">
            <span class="total-count">{{ Meals.totalCount }}</span>
        </div>

        <div class="total-amount">
            <p class="no-goods" v-show="Meals.totalCount == 0">未选择商品</p>
            <p class="has-goods" v-show="Meals.totalCount > 0">{{ Meals.totalPrice }}</p>
        </div>
        <button class="checkout">去结算</button>
    </div>
</template>

<style scoped>
.cart-bar{
    width: 710rem;
    height: 100rem;
    position: fixed;
    bottom: 40rem;
    left: 0;
    right: 0;
    margin: 0 auto;
    background-color: rgb(58,58,58);
    border-radius: 50rem;
    z-index: 20;
}

.cart-bag{
    width: 100rem;
    position: absolute;
    bottom: -10rem;
}
.total-count{
    width: 45rem;
    height: 45rem;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    background: rgb(255, 71, 71);
    position: absolute;
    right: -20rem;
    top: 10rem;
    padding: 8rem;
    font-size: 25rem;
    font-weight: 700;
    color: #fff;
}
.total-amount{
    display: flex;
    align-items: center;
    margin-left: 140rem;
    color: #fff;
    font-size: 36rem;
    height: 100%;
    font-weight: 700;
}
.no-goods{
    color: rgb(148, 148, 148);
}
.has-goods::before{
    content: "￥";
    font-size: 26rem;
}
.checkout{
    position: absolute;
    top: 0;
    right: 0;
    height: 100%;
    border: none;
    width: 180rem;
    border-radius: 50rem;
    font-size: 30rem;
    font-weight: 700;
    background-color: rgb(248,188,0);
}
</style>