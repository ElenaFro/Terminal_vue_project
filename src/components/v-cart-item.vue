<template>
    <div class="v-cart-item">
        <img class="v-cart-item__image" :src="('../src/assets/images/' + cart_item_data.image)" alt="picture"/>
        <div>
            <p>{{ cart_item_data.name }}</p>
            <p>{{ cart_item_data.price }}</p>
            <p>{{ cart_item_data.article }}</p>
            <p>{{ cart_item_data.about }}</p>
        </div>
        <div class="v-cart-item__quantity">
            <p>Quantity</p>
            <span>
                {{ cart_item_data.quantity }}
            </span>
        </div>
        <button class=" pink btn" @click="deleteFromCart">Удалить</button>
    </div>
</template>

<script>
export default {
    name: 'v-cart-item',
    props: {
        cart_item_data: {
            type: Object,
            default(){
                return {}
            }
        }
    },
    data () {
        return {
            title: 'hello!'
        }
    },
    computed: {},
    methods: {
        deleteFromCart () {
            this.$emit('deleteFromCart')
        }
    },
    // watch: {},
    // created () { },
    mounted () {
        console.log("cart-item")
    }
}
</script>

<style>
.v-cart-item {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    align-items: center;
    flex-basis: 25%;
    box-shadow: 0 0 4px 0 rgb(160, 160, 160);
    padding: 20px;
    margin: 20px;
    padding-top: 40px;
} 

.v-cart-item__image {
    min-width: 10%;
}
</style>