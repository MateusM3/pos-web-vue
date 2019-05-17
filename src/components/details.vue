<template>
	<div class="details">
		<div class="container">
			<div class="row">
				<div class="col-md-12" v-for="(product,index) in products" :key="index"> 
					<div v-if="proId == product.productId">
						<h1>{{product.productTitle}}</h1>
						<img :src="product.image" class="img-fluid">
					</div>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
	export default{
		name:'details',
		data(){
			return{
				proId:this.$route.params.Pid,
				title:"details",
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
		}
		
	}
</script>
