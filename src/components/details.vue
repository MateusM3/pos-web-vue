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
          <div @click="goTodetail(data.productId)" class="produto col-12 col-sm-6 col-xl-3"  v-for="(data,index) in products" :key="index"  v-if="index < 4">
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
            </div>
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
            pricediscont: "R$1.800,00",
            description: 'O Sistema do PS4 foca nos jogadores, garantindo que os melhores jogos e a experiência mais imersiva seja possível na plataforma. O Console possui seu poder gráfico baseado em um processador poderoso, que possui oito núcleos funcionando a 64 bits.\n' +
              'Entre em diversos desafios com sua comunidade gamer e compartilhe seus triúnfos épicos ao apertar um simples botão, com as novas funcionalidades de Streaming, gravação de vídeo e screenshots.\n' +
              'O Playstation 4 SLIM, é o modelo mais fino, mais leve e agora sem suas bordas tão retas, lembrando um paralelepípedo. Os botões também sofreram mudanças, eles não são mais eletrostáticos, voltando a serem mecânicos. O PS4 SLIM é a versão compacta do bom, e velho PS4 FAT, contando com inúmeros jogos e clássicos remasterizados, além das muitos jogos exclusivos da Sony.',
          },
          {
            productTitle:"X-Box One",
            image       : require('../assets/images/item2.png'),
            productId:2,
            price: "R$2050,00",
            pricediscont: "R$2.000,00",
            istallments: {
              qty: 'x5',
              value: 'R$25'
            },
            is_new: true,
            discont: false,
            description: 'Console Xbox One S Microsoft 1TB + Controle Wireless\n' +
              'O Xbox One S, 40% Menor, 1TB de armazenamento e fonte de alimentação interna.\n' +
              'Experimente os melhores jogos, incluindo clássicos do Xbox 360, em um console 40% menor. \n' +
              'Não se engane com o tamanho: com uma fonte de alimentação interna e até 1TB de armazenamento interno, o Xbox One S é o Xbox mais avançado que já existiu.',
          },
          {
            productTitle:"Nintendo",
            price: "R$2.000,00",
            pricediscont: "R$1.800,00",
            image       : require('../assets/images/item3.png'),
            productId:3,
            istallments: {
              qty: 'x5',
              value: 'R$25'
            },
            discont: '5%',
            description: 'O Nintendo Switch, além de funcionar também como um console clássico, pode ser simplesmente transformado em um portátil. Ele traz 1 controle (Joy Con) que pode ser acoplado a uma mini tela (6,2 polegadas e multi-touch). Isso faz dele um videogame híbrido.',
          },
          {
            productTitle:"Mouse Longitec",
            image       : require('../assets/images/item4.png'),
            productId:4,
            price: "R$450,00",
            pricediscont: "R$400,00",
            istallments: {
              qty: 'x5',
              value: 'R$25'
            },
            is_new: false,
            discont: '10%',
            description: 'Torne-se mais preciso do que nunca. O G403 oferece o sensor para jogos mais avançado do mundo, usado por profissionais eSports em todo o mundo. Excepcionalmente preciso e consistente, ele permite que você tenha respostas mais rápidas e maior precisão de mira.',
          },
          {
            productTitle:"Teclado",
            image       : require('../assets/images/item5.png'),
            productId:5,
            price: "R$200,00",
            pricediscont: "R$180,00",
            istallments: {
              qty: 'x5',
              value: 'R$25'
            },
            is_new: false,
            discont: false,
            description: 'O HyperX Alloy Fps Pro destina-se ao jogador de Fps que deseja um teclado confiável e sem teclado numérico (Tkl) para maximizar o espaço. Este teclado de 87 teclas oferece tudo o que um jogador profissional precisa, mas sem o teclado numérico. O Alloy Fps Pro apresenta as teclas com switch Cherry Mx Red e sua estrutura sólida em aço assegura que você terá uma plataforma sólida durante seus jogos. Seu modelo ultra mínimo e o cabo removível tornam o teclado superportátil, mas ainda recheado de recursos Modo Jogo, funções 100% Anti-Ghosting, N-Key rollover, iluminação vermelha e efeitos dinâmicos HyperX para acentuar o estilo do seu computador.\n',
          },
          {
            productTitle:"Smart Tv",
            image       : require('../assets/images/item6.png'),
            productId:6,
            price: "R$1.000,00",
            pricediscont: "R$1.800,00",
            istallments: {
              qty: 'x5',
              value: 'R$25'
            },
            is_new: false,
            discont: false,
            description: 'A Smart TV PTV32G50SN da Philco com tela LED de 32" é a tecnologia que falta na sua casa. Ela possui o aplicativo oficial da Netflix, Wi-Fi que proporciona interatividade com programas de TVs digitais pelo controle remoto, sistema operacional Linux, conversor digital integrado, entradas HDMI e USB, RJ45, RCA, RF, Wireless e T-Link. Conta ainda com processador Duo Core proporcionando maior velocidade e performance para o seu televisor.',
          }
        ]
			}
		}
    ,
    methods:{
      goTodetail(prodId) {
        let proId = prodId
        this.$router.push({name:'details',params:{Pid:proId}})
      }
    }
		
	}
</script>
