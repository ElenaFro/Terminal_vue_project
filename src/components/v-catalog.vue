<template>
  <h1 class="title">Керамические вазы</h1>
  <div class="v-catalog">
    <router-link :to="{ name: 'cart', params: { cart_data: CART } }">
      <div class="v-catalog__link_to_cart  pink-text">
        <i class="medium material-icons pink-text text-darken-2">shopping_cart</i>
        {{ CART.length }}</div>
    </router-link>
    <div class="v-catalog__list">
      <vCatalogItem v-for="product in PRODUCTS" :key="product.article" :product_data="product" @addToCart="addToCart" />
    </div>
    <!-- v-bind перед product можно опустить, оставить только : -->
  </div>
</template>

<script>
import vCatalogItem from './v-catalog-item.vue'
import { mapActions, mapGetters } from 'vuex'

export default {
  name: 'v-catalog',
  components: {
    vCatalogItem
  },
  props: {},
  data() {
    return {}
  },
  computed: {
    ...mapGetters(['PRODUCTS', 'CART']),
  },
  methods: {
    ...mapActions(['GET_PRODUCTS_FROM_API', 'ADD_TO_CART']),
    addToCart(data) {
      this.ADD_TO_CART(data)
    }
  },
  mounted() {
    this.GET_PRODUCTS_FROM_API().then((response) => {
      if (response.data) {
        console.log("данные пришли")
      }
    })
  }
}

</script>

<style>
.v-catalog,
.v-catalog__list {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  align-items: center;
}

.v-catalog__link_to_cart {
  position: absolute;
  top: 10px;
  right: 10px;
  padding: 15px;
  font-size: 26px;
}
.title {
  margin-bottom: 60px;
}
</style>
