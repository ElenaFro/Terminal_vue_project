<template>
  <div class="v-cart">
    <router-link :to="{ name: 'catalog' }">
      <div class="v-catalog__link_to_cart">cart:{{ CART.length }}</div>
      <button>Back to catalog</button>
    </router-link>

    <p v-if="!CART.length">Вы ничего сюда не положили...</p>

    <h1>Корзина</h1>
    <vCartItem 
      v-for="(item, index) in CART" 
      :key="item.article"
      :cart_item_data="item" 
      @deleteFromCart="deleteFromCart(index)"
    />
  </div>

</template>

<script>
import vCartItem from './v-cart-item.vue'
import { mapActions, mapGetters } from 'vuex'
export default {
  name: 'v-cart',
  components: {
    vCartItem
  },
  props: {
    cart_data: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {}
  },
  computed: {
    ...mapGetters(['CART'])
  },
  methods: {
    ...mapActions(['DELETE_FROM_CART']),
    deleteFromCart(index) {
      this.DELETE_FROM_CART(index)
    } 
  }
}
</script>

<style scoped>
.v-cart {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  color: grey;
  font-size: 20px;
  margin-bottom: 150px;
}
p{
  text-align: center;
  font-size: 26px;
}
</style>