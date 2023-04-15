<script setup>
    import Counter from "../UI/Counter.vue"
    const props = defineProps(['meal'])
    const meal = props.meal
</script>
<template>
    <div class="meal">
        <div class="img">
            <img :src="meal.img" alt="">
        </div>
        <div class="info">
            <div class="desc">
                <h2>{{ props.meal.title }}</h2>
                <p>{{ props.meal.desc }}</p>
            </div>
            <div class="price_btn">
                <span class="price">{{ props.meal.price }}</span>
                <Counter></Counter>
            </div>
        </div>

    </div>
</template>

<style scoped>
    .meal{
        padding: 0 20rem;
        display: flex;
        align-items: center;
        height: 280rem;
        border-bottom: 1px solid #e6e6e6;
    }

    .img{
        width: 200rem;
    }

    .info{
        width: 510rem;
        margin-left: 20rem;
        padding-right: 40rem;
    }

    .info h2{
        color: #000;
        font-size: 30rem;
    }

    .info p{
        color: #9b9b9b;
        font-size: 24rem;
    }

    .price_btn{
        margin-top: 40rem;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }

    .price{
        font-size: 30rem;
        font-weight: 700;
    }
    .price::before{
        content: "￥";
    }
</style>