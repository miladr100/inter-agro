<template>
  <v-row justify="center" class="mt-4">
    <v-row justify="center" class="mt-4">
      <v-col cols="12" sm="10" md="10">
        <v-card class="d-flex flex-column align-center">
          <v-card-title class="text-h3 font-weight-bold">
            Nossa História
          </v-card-title>

          <v-row>
            <v-col cols="6">
              <v-card-text class="text-h6 text--primary font-weight-regular text-justify">
                A sensibilização e a organização de cadeias para exportação começaram em 2016, com os tradicionais seminários da Rede InterAgro. Como resultado positivo, os empresários rurais passaram a solicitar ações mais estruturadas e continuadas de apoio a exportações. Também se percebeu que estes encontravam dificuldades para comercialização no exterior.
              </v-card-text>
            </v-col>

            <v-col cols="6">
              <v-card-text class="text-h6 text--primary font-weight-regular text-justify">
                A sensibilização e a organização de cadeias para exportação começaram em 2016, com os tradicionais seminários da Rede InterAgro. Como resultado positivo, os empresários rurais passaram a solicitar ações mais estruturadas e continuadas de apoio a exportações. Também se percebeu que estes encontravam dificuldades para comercialização no exterior.
              </v-card-text>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>

    <v-row justify="center" align="center" class="mt-12">
      <v-card-title class="text-h4 font-weight-bold">
        Essas são algumas de nossas negociações
      </v-card-title>
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
import imagCarrousel01 from '~/static/img/index_carrousel/index_carrousel_01.jpeg';
import imagCarrousel02 from '~/static/img/index_carrousel/index_carrousel_02.jpeg';
import imagCarrousel03 from '~/static/img/index_carrousel/index_carrousel_03.jpeg';
import imagCarrousel04 from '~/static/img/index_carrousel/index_carrousel_04.jpeg';
import imagCarrousel05 from '~/static/img/index_carrousel/index_carrousel_05.jpeg';
import imagCarrousel06 from '~/static/img/index_carrousel/index_carrousel_06.jpeg';

export default {
    data () {
      return {
        items: [
          {
            title: "Sementes de Pastagem",
            texts: [
              "Através da parceria e cooperação com empresas do ramo, temos campos de produção na maioria das regiões produtoras de sementes no país.",
              "Todo o sistema de produção é desenvolvido a partir de tecnologias já consagradas, que consideram, não somente a produção otimizada, mas também o respeito pleno ao meio ambiente, resultando em um sistema de produção sustentável."
            ],
            rightDirection: false,
            carrousel: [
              { src: imagCarrousel01 },
              { src: imagCarrousel02 },
              { src: imagCarrousel03 },
              { src: imagCarrousel04 },
              { src: imagCarrousel05 },
              { src: imagCarrousel06 },
            ]
          },
          {
            title: "Frigoríficos",
            texts: [
              "evando sabor e qualidade para a mesa de milhares de pessoas todos os dias através dos cortes das carnes, os frigoríficos brasileiros vêm conquistando os mais variados paladares em diversos países no mundo todo.",
              "Os padrões de fabricação das empresas parceiras são repletos de cuidado e segurança. Nosso objetivo é oferecer um produto competitivo e uma carne mais saborosa."
            ],
            rightDirection: true,
            carrousel: [
              { src: imagCarrousel01 },
              { src: imagCarrousel02 },
              { src: imagCarrousel03 },
              { src: imagCarrousel04 },
              { src: imagCarrousel05 },
              { src: imagCarrousel06 },
            ]
          },
          {
            title: "Grãos e Milho",
            texts: [
              "O Brasil está entre os maiores produtores de grãos, e o milho não fica de fora nesta lista.",
              "Vale lembrar que o País exportou 4,8 milhões de toneladas em 2004, movimentando US$ 166 milhões. Essa produção, transformada em alimentos e produtos acabados, pode agregar receita de maior valor.",
              "O aumento do consumo humano de milho, como se vê, é um esforço que interessa a todos os elos da cadeia produtiva e aos mais de 180 milhões de brasileiros.",
              "O milho brasileiro é seleto em qualidade e muito bem pontuado nos mercados mundiais. "
            ],
            rightDirection: false,
            carrousel: [
              { src: imagCarrousel01 },
              { src: imagCarrousel02 },
              { src: imagCarrousel03 },
              { src: imagCarrousel04 },
              { src: imagCarrousel05 },
              { src: imagCarrousel06 },
            ]
          }
        ]
      }
  }
}
</script>
