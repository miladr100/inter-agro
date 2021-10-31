<template>
  <v-row justify="center" class="mt-4">
    <v-row justify="center" class="mt-4">
      <v-col cols="12" md="10" sm="10" class="mt-4">
        <v-card>
          <v-card-text class="text-h6 text--primary font-weight-regular text-justify">
            O Agro.BR, convênio entre a CNA e Apex-Brasil, é um projeto de internacionalização que vai sensibilizar, capacitar, planejar e viabilizar geração de negócios internacionais para pequenos e médios empresários rurais brasileiros. Tem como objetivos organizar a oferta de produtos e aumentar a quantidade de empresários rurais no comércio exterior, diversificando a pauta de produtos exportados pelo Brasil.
          </v-card-text>
          <v-card-text class="text-h6 text--primary font-weight-regular text-justify">
            A sensibilização e a organização de cadeias para exportação começaram em 2016, com os tradicionais seminários da Rede InterAgro. Como resultado positivo, os empresários rurais passaram a solicitar ações mais estruturadas e continuadas de apoio a exportações. Também se percebeu que estes encontravam dificuldades para comercialização no exterior.
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="4" md="3" sm="3">
        <v-card
            color="grey darken-1"
            dark
          >
          <v-card-title class="text-h5">
            Unlimited music now
          </v-card-title>

          <v-card-subtitle>Listen to your favorite artists and albums whenever and wherever, online and offline.</v-card-subtitle>

          <v-card-actions>
            <v-btn text>
              Listen Now
            </v-btn>
          </v-card-actions>
        </v-card>

        <v-card
          class="mt-8"
          color="grey darken-2"
          dark
        >
          <v-card-title class="text-h5">
            Unlimited music now
          </v-card-title>

          <v-card-subtitle>Listen to your favorite artists and albums whenever and wherever, online and offline.</v-card-subtitle>

          <v-card-actions>
            <v-btn text>
              Listen Now
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>

      <v-col cols="8" md="8" sm="8">
        <v-card>
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
                v-for="(item,i) in items"
                :key="i"
                :src="item.src"
                reverse-transition="fade-transition"
                transition="fade-transition"
              ></v-carousel-item>
            </v-carousel>
          </v-container>

          <v-card-title class="text-h4 font-weight-bold">
            Intermediária de Importação e Exportação
          </v-card-title>

          <v-card-text class="text-h6 text--primary text-justify">
            Um bem-sucedido modelo internacional de grandes empresas do Agronegócio
            levando o  Brasil para o mundo ao exportar, em grande volumes Grãos, Carnes, Commodities Agrícolas e Derivados, além de distribuir alguns destes.
          </v-card-text>

          <v-card-actions>
            <v-btn
              color="light-green darken-3"
              text
              @click="$router.push('/bussiness')"
            >
              Nossos Negócios
            </v-btn>
            <v-spacer></v-spacer>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="12" md="8" sm="8">
        <v-card>
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
                v-for="(item,i) in items"
                :key="i"
                :src="item.src"
                reverse-transition="fade-transition"
                transition="fade-transition"
              ></v-carousel-item>
            </v-carousel>
          </v-container>

          <v-card-title class="text-h4 font-weight-bold">
            Intermediária de Importação e Exportação
          </v-card-title>

          <v-card-text class="text-h6 text--primary text-justify">
            Um bem-sucedido modelo internacional de grandes empresas do Agronegócio
            levando o  Brasil para o mundo ao exportar, em grande volumes Grãos, Carnes, Commodities Agrícolas e Derivados, além de distribuir alguns destes.
          </v-card-text>

          <v-card-actions>
            <v-btn
              color="light-green darken-3"
              text
              @click="$router.push('/bussiness')"
            >
              Nossos Negócios
            </v-btn>
            <v-spacer></v-spacer>
          </v-card-actions>
        </v-card>
      </v-col>

      <v-col cols="4" md="3" sm="3">
        <v-card
          color="green darken-1"
          dark
        >
          <v-card-title class="text-h5">
            Unlimited music now
          </v-card-title>

          <v-card-subtitle>Listen to your favorite artists and albums whenever and wherever, online and offline.</v-card-subtitle>

          <v-card-actions>
            <v-btn text>
              Listen Now
            </v-btn>
          </v-card-actions>
        </v-card>

        <v-card
          class="mt-8"
          color="green darken-2"
          dark
        >
          <v-card-title class="text-h5">
            Unlimited music now
          </v-card-title>

          <v-card-subtitle>Listen to your favorite artists and albums whenever and wherever, online and offline.</v-card-subtitle>

          <v-card-actions>
            <v-btn text>
              Listen Now
            </v-btn>
          </v-card-actions>
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
          { src: imagCarrousel01 },
          { src: imagCarrousel02 },
          { src: imagCarrousel03 },
          { src: imagCarrousel04 },
          { src: imagCarrousel05 },
          { src: imagCarrousel06 },
        ],
      }
    }
}
</script>