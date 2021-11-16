<template>
  <v-row justify="center" class="mt-4">
    <v-row justify="center" class="mt-4">
      <v-col cols="12" sm="10" md="10">
        <v-card class="d-flex flex-column align-center" elevation="2" tile>
          <v-card-title class="text-h3 font-weight-bold">
            Nossos Negócios
          </v-card-title>
        </v-card>
      </v-col>
    </v-row>

    <v-row v-for="item in items" :key="item.title" justify="center" class="mt-4">
      <v-col cols="12" sm="10" md="10">
        <v-card>
          <v-row justify="center" align="center" class="mt-4">
            <v-col v-if="!item.rightDirection" cols="7">
              <v-card-title class="text-h4 font-weight-bold">
                {{item.title}}
              </v-card-title>
              <v-card-text v-for="(text,ind) in item.texts" :key="ind" class="text-h7 text-justify">   
                {{text}}
              </v-card-text>
            </v-col>
            <v-col cols="5">
              <v-container>
                <v-carousel
                  :cycle="true"
                  :show-arrows="false"
                  hide-delimiter-background
                  delimiter-icon="mdi-minus"
                  height="380"
                  width="200"
                >
                  <v-carousel-item
                    v-for="(carrouselItem,index) in item.carrousel"
                    :key="index"
                    :src="carrouselItem.src"
                    reverse-transition="fade-transition"
                    transition="fade-transition"
                  ></v-carousel-item>
                </v-carousel>
              </v-container>
            </v-col>
            <v-col v-if="item.rightDirection" cols="7">
              <v-card-title class="text-h4 font-weight-bold">
                {{item.title}}
              </v-card-title>
              <v-card-text v-for="(text,ind) in item.texts" :key="ind" class="text-h7 text-justify">   
                {{text}}
              </v-card-text>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
  </v-row>
</template>

<script>
import negocios01 from '~/static/img/negocios/negocios_01.jpeg';
import negocios02 from '~/static/img/negocios/negocios_02.jpg';
import negocios03 from '~/static/img/negocios/negocios_03.jpeg';

export default {
    data () {
      return {
        items: [
          {
            title: "Agronegócios",
            texts: [
              "Oferecemos soluções completas para cada desafio logístico, comercial ou financeiro, levando o Brasil para o mundo. Operamos também com Barter, garantindo que o produtor tenha acesso aos insumos necessários para cultivar produtos com a qualidade exigida e contratada na outra ponta da negociação."
            ],
            rightDirection: false,
            carrousel: [
              { src: negocios01 },
            ]
          },
          {
            title: "Açúcar",
            texts: [
              "Através de uma estrutura interna robusta e uma experiente equipe no setor sucroalcooleiro, possuímos parcerias sólidas com produtores e clientes, buscando atender as necessidades de ambos, comprador e vendedor, nas negociações que realizamos.",
              "Sabemos da importância de cada aspecto da operação na garantia da qualidade do produto que chegará ao consumidor.",
              "Por isso, estamos integrados em toda a cadeia de suprimentos, desde a produção até a entrega do açúcar em diversos países."
            ],
            rightDirection: true,
            carrousel: [
              { src: negocios02 },
            ]
          },
          {
            title: "Grãos",
            texts: [
              "​Levar o Brasil para o mundo, abastecendo países , com os principais produtos agrícolas brasileiros, requer uma estrutura inteligente, otimizada e flexível para atender às particularidades exigidas por cada produto e mercado.",
              "É dessa forma que nós atuamos ao longo de toda a cadeia de exportação de grãos, fazendo a originação e oferecendo os mais competitivos serviços de logística multimodal door to door, escoando os produtos desde as fazendas até os principais portos das regiões Sul e Sudeste."
            ],
            rightDirection: false,
            carrousel: [
              { src: negocios03 },
            ]
          }
        ]
      }
  }
}
</script>
