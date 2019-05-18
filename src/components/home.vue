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
  import Slider from './slider'
export default {
  name: 'home',
  data () {
    return {
      title: 'Produtos em Destaque',
      products:[
      {
        productTitle:"PS4",
        image       : require('../assets/images/item1.png'),
        productId:1,
        price: "R$2.000,00",
        istallments: {
          qty: 'x5',
          value: 'R$25'
        },
        is_new: true,
        discont: '15%',
      },
      {
        productTitle:"X-Box One",
        image       : require('../assets/images/item2.png'),
        productId:2,
        price: "R$2050,00",
        istallments: {
          qty: '5',
          value: 'R$25'
        },
        is_new: true,
        discont: false,
      },
      {
        productTitle:"Nintendo",
        price: "R$2.000,00",
        image       : require('../assets/images/item3.png'),
        productId:3,
        istallments: {
          qty: 'x5',
          value: 'R$25'
        },
        discont: '5%',
      },
      {
        productTitle:"Mouse Longitec",
        image       : require('../assets/images/item4.png'),
        productId:4,
        price: "R$450,00",
        istallments: {
          qty: 'x5',
          value: 'R$25'
        },
        is_new: false,
        discont: '10%',
      },
      {
        productTitle:"Teclado",
        image       : require('../assets/images/item5.png'),
        productId:5,
        price: "R$200,00",
        istallments: {
          qty: 'x5',
          value: 'R$25'
        },
        is_new: false,
        discont: false,
      },
      {
        productTitle:"Smart Tv",
        image       : require('../assets/images/item6.png'),
        productId:6,
        price: "R$1.000,00",
        istallments: {
          qty: 'x5',
          value: 'R$25'
        },
        is_new: false,
        discont: false,
      }
      ]
    }
  },
  methods:{
  goTodetail(prodId) {
    let proId=prodId
    this.$router.push({name:'details',params:{Pid:proId}})
  }
  },
  components: {
    'component-slider': Slider
  },
}
</script>

