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
              <a href="#" class="add-carrinho">Adicionar ao Carrinho</a>
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
        ],
        methods:{
          goTodetail(prodId) {
            let proId = prodId
            this.$router.push({name:'details',params:{Pid:proId}})
          }
        }
				 
			}
		}
		
	}
</script>

<style>

  .btn-comprar {
    display: block;
    overflow: hidden;
    padding: 9px 0;
    margin-top: 5px;
    border-top: 2px solid #3e3e3e;
  }
  .btn-comprar a {
    width: 100%;
    color: #fff;
    background-color: rgb(66, 185, 131);
    padding: 12px;
    border-radius: 10px;
    display: block;
    font-weight: 700;
    text-align: center;
  }

  .details .valores {
    margin-top: 119px;
  }

  .details .valores .valor {
    width: 100%;
    overflow: hidden;
    display: table;
  }
  .details .valores .valor .a-vista {
    font-weight: 700;
    font-size: 36px;
    display: table-cell;
    vertical-align: middle;
    color: rgb(66, 185, 131);
  }

  .details .valores .valor .preco{
    font-size: 14px;
    text-decoration: line-through;
    display: table-cell;
    vertical-align: middle;
    text-align: right;
  }

  .details .valores .parcela {
    font-size: 24px;
    line-height: 29px;
    font-weight: 700;
    margin-bottom: 3px;
  }

/*  Listagem de produtos */
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
    width: 76%;
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
