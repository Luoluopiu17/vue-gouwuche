<template>
  <div class="app">
    <MyHeader name="购物车案例" color="lightyellow"></MyHeader>
    <MyGoods :goods="item" v-for="item in goodsList" :key="item.goods_id"></MyGoods>
    <MyFooter :goodsList="goodsList"></MyFooter>
  </div>
</template>

<script>
import MyHeader from '@/components/MyHeader.vue'
import MyGoods from '@/components/MyGoods.vue'
import MyFooter from '@/components/MyFooter.vue'
import axios from 'axios'
export default {
  components: {
    MyHeader,
    MyGoods,
    MyFooter
  },
  data() {
    return {
      goodsList: []
    }
  },
  created() {
    this.getList()
  },
  methods: {
    async getList() {
      const res = await axios({
        url: '/api/cart'
      })
      this.goodsList = res.data.list
    }
  }
}
</script>

<style>
.app {
  padding: 50px 0;
}
</style>
