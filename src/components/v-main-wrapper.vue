<template>
    <div class="v-main-wrapper">
      <!-- <router-view></router-view> -->
      <!-- <keep-alive>
        <router-view></router-view>
      </keep-alive> -->
      <!-- <router-view> больше нельзя использовать непосредственно внутри <transition> или <keep-alive>.
Вместо этого используйте реквизиты слотов: -->

<router-view v-slot="{ Component }">
  <keep-alive>
    <component :is="Component" />
  </keep-alive>
</router-view>

      <!-- <vCatalog />
      <vCart v-if="CART.length" :cart_data="CART" /> -->
    </div>
</template>
  
<script>
// import vCatalog from './v-catalog.vue'
// import vCart from './v-cart.vue'
import { mapGetters } from 'vuex'
  
export default {
    name: 'v-main-wrapper',
    // components: { vCatalog, vCart },
    props: {},
    data () {
      return {
        title: 'hello!'
      }
    },
    computed: {
      ...mapGetters(['CART'])
    },
    methods: {},
    watch: {},
    created () {},
    mounted () {
      console.log("hello i'm here,v-main-wrapper ")
    }
}
</script>
  
<style>
.v-main-wrapper {
    max-width: 900px;
    margin: 0 auto;
}
</style>