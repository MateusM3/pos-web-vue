<template>
  <div class="home">
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
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.row img{
  max-height: 15em;
  width: 100%;

}
.row .produto {
  cursor:pointer;
}

.produtos .produto {
  display: table-cell;
  display: -webkit-box;
  display: -moz-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  -webkit-justify-content: flex-start;
  justify-content: flex-start;
  flex-direction: column;
  -webkit-flex-direction: column;
  -ms-flex-direction: column;
  flex-flow: row wrap;
  -webkit-flex-flow: row wrap;
  outline: none;
  position: relative;
  text-align: center;
  padding: 10px 15px;
  margin-bottom: 40px;
  vertical-align: top;
  -webkit-transition: all 0.2s ease;
  -moz-transition: all 0.2s ease;
  -ms-transition: all 0.2s ease;
  -o-transition: all 0.2s ease;
  transition: all 0.2s ease;
}

.produtos .produto .box {
  width: 100%;
  color: #3e3e3e;
  padding: 20px 20px 65px 20px;
  position: relative;
  display: -webkit-box;
  display: -moz-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  flex-flow: row wrap;
  -webkit-flex-flow: row wrap;
  -webkit-align-content: space-between;
  align-content: space-between;
  -webkit-box-shadow: 5px 5px 8px -1px rgba(0, 0, 0, 0.1);
  -moz-box-shadow: 5px 5px 8px -1px rgba(0, 0, 0, 0.1);
  -o-box-shadow: 5px 5px 8px -1px rgba(0, 0, 0, 0.1);
  -ms-box-shadow: 5px 5px 8px -1px rgba(0, 0, 0, 0.1);
  box-shadow: 5px 5px 8px -1px rgba(0, 0, 0, 0.1);
}

.produtos .produto .box .header-prod, .produtos .produto .box .footer-prod {
  width: 100%;
  display: inline-block;
}

.produtos .produto .box .bandeiras {
  width: 100%;
  position: absolute;
  top: 13px;
  right: 0;
  z-index: 5;
}

.produtos .produto .box .bandeiras span {
  color: #fff;
  font-weight: 700;
  height: 35px;
  font-size: 18px;
  padding: 3px 17px;
  line-height: 30px;
}

.produtos .produto .box .bandeiras span.desconto {
  float: right;
  background-color: #42b983;
  border-top-left-radius: 100px;
  border-bottom-left-radius: 100px;
}

.produtos .produto .box .bandeiras span.novo {
  float: left;
  background-color:  #42b983;
  border-top-right-radius: 100px;
  border-bottom-right-radius: 100px;
}

.produtos .produto .box .thumb {
  height: 200px;
  margin-bottom: 15px;
  position: relative;
}

.produtos .produto .box .thumb img {
  max-width: 100%;
  max-height: 100%;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  margin: auto;
}

.produtos .produto .box .descr-produto {
  -webkit-transition: all 0.2s ease;
  -moz-transition: all 0.2s ease;
  -ms-transition: all 0.2s ease;
  -o-transition: all 0.2s ease;
  transition: all 0.2s ease;
}

.produtos .produto .box .descr-produto p {
  font-weight: 700;
  font-size: 18px;
  line-height: 20px;
  margin-bottom: 3px;
}

.produtos .produto .box .descr-produto span {
  font-size: 14px;
}

.produtos .produto .box .info-produto {
  font-size: 16px;
  font-weight: 700;
  line-height: 20px;
  color: #42b983;
}

.produtos .produto .box .info-produto .preco, .produtos .produto .box .info-produto header .navbar .carrinho .conteudo ul li.cart-footer .total, header .navbar .carrinho .conteudo ul li.cart-footer .produtos .produto .box .info-produto .total {
  font-size: 26px;
  line-height: 23px;
  display: block;
  padding-top: 1px;
}

.produtos .produto .add-carrinho {
  width: 70%;
  font-size: 16px;
  font-weight: 700;
  color: #42b983;
  border-top: 2px solid #42b983;
  position: absolute;
  left: 15%;
  bottom: 25px;
  padding: 7px 7px 9px 7px;
}

.produtos .produto .add-carrinho:hover {
  color: #fff;
  border-color: #33754d !important;
  background-color: #33754d !important;
}

.produtos .produto:hover {
  transform: scale(1.05);
}

.produtos .produto:hover .box .descr-produto {
  color: #42b983;
}

.produtos .produto:hover .add-carrinho {
  color: #fff;
  background-color: #42b983;
}

</style>
