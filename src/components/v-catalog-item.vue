<template>
    <div class="v-catalog-item">
        <img class="v-catalog-item_image" :src="('../src/assets/images/' + product_data.image)" alt="picture"/>
        <p class="v-catalog-item__name">{{ product_data.name }}</p>
        <p class="v-catalog-item__price">{{ product_data.price }}</p>
        <p class="v-catalog-item__about">{{ product_data.about }}</p>
        <button class="v-catalog-item__add_to_cart_btn  pink btn" @click="addToCart">В корзину</button>
    </div>
</template>
<script>
export default {
    name: 'v-catalog-item',
    props: {
        product_data: {
            type: Object,
            default() {
                return {}
            }
        }
    },
    data() {
        return {}
    },
    methods: {
        addToCart() {
            this.$emit('addToCart', this.product_data)
        }
    }
}
</script>
<style lang="scss">
.v-catalog-item {
    flex-basis: 40%;
    box-shadow: 0 0 4px 0 rgb(160, 160, 160);
    padding: 20px;
    margin: 20px;
}
.v-catalog-item_image {
    width: 160px;
    display: block;
    margin: 0 auto;
}
</style>