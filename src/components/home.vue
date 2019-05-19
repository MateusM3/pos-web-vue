<template>
  <div class="home">
    <component-slider></component-slider>
    <h1>{{title}}</h1>
    <div class="row produtos">
      <div @click="goTodetail(data.productId)" class="produto col-12 col-sm-6 col-xl-4"  v-for="(data,index) in products" :key="index">
        <div class="box">
          <div class="header-prod">
            <div class="bandeiras">
              <span v-show="data.discont" class="desconto">-{{data.discont}}</span>
               <span v-show="data.is_new" class="novo">NOVO</span>
            </div>
            <div class="thumb">
              <img :src="data.image" class="img-fluid">
            </div>
            <div class="descr-produto">
              <p>{{data.productTitle}}</p>
              <span><strong>à vista {{data.price}}</strong> ou {{data.istallments.qty}} de {{data.istallments.value}}</span>
            </div>
          </div>
          <div class="footer-prod">
            <div class="info-produto">
              <p class="preco">{{data.price}}</p>
              <p>à vista no boleto</p>
            </div>
          </div>
          <a href="#" class="add-carrinho">Adicionar ao Carrinho</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Vue from 'vue'
  import Slider from './slider'
  import axios from 'axios'

export default {
  name: 'home',
  data () {
    return {
      title: 'Produtos em Destaque',
      products: []
    }
  },
  created() {
    //utilizando ajax para buscar os produtos.
    axios.get(`http://localhost:3000/products`)
      .then((response) => {
        this.products = response.data
        return 'Axios'
      });

    return  'Axios';
  },
  methods:{
  goTodetail(prodId) {
    let proId = prodId
    this.$router.push({name:'details',params:{Pid:proId}})
  }
  },
  components: {
    'component-slider': Slider
  },
}
</script>

