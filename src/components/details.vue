<template>
	<div class="details">
		<div class="container">
			<div class="row">
				<div class="col-md-12" v-for="(product,index) in products" :key="index">
					<div v-if="proId == product.productId">
            <div class="row">
              <div class="col-12 col-sm-6 col-lg-6">
                <img :src="product.image" class="img-fluid">
              </div>
              <div class="col-12 col-sm-6 col-md-6 offset-md-1 offset-lg-0 col-lg-6">
                <div class="valores">
                  <div class="valor">
                    <span class="a-vista">{{product.price}}</span>
                    <span class="preco">de {{product.pricediscont}}</span>
                  </div>
                  <p class="parcela">{{product.istallments.qty}} de {{product.istallments.value}}</p>
                  <div class="btn-comprar">
                    <a href="#">COMPRAR</a>
                  </div>
                </div>
              </div>
            </div>
            <div class="row">
              <div class="col-12 col-lg-12">
                <div class="info">
                  <h1 class="nome-produto">{{product.productTitle}}</h1>
                  <p>
                    {{product.description}}
                  </p>
                </div>
              </div>
            </div>
					</div>
				</div>
			</div>
      <div class="row">
        <h3>Produtos Relacionados</h3>
        <div class="row produtos">
          <div class="produto col-12 col-sm-6 col-xl-3"  v-for="(data,index) in products" :key="index"  v-if="index < 4">
            <div class="box" @click="goTodetail(data.productId)">
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
            </div>
          </div>
        </div>

      </div>
		</div>
	</div>

</template>
<script>
  import axios from 'axios'

	export default{
		name:'details',
		data(){
			return{
				proId:this.$route.params.Pid,
				title:"details",
        products: []
			}
		}
    ,
    created() {
      axios.get(`http://localhost:3000/products`)
        .then((response) => {
          this.products = response.data;
          return 'Axios'
        });

      return  'Axios';
    },
    methods:{
      goTodetail(prodId) {
        let proId = prodId;
        this.$router.push({name:'details', params:{Pid:proId}})
      }
    }
		
	}
</script>
