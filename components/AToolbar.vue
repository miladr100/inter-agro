<template>
  <div>
    <v-toolbar
      dark
      extended
      extension-height="140"
      :src="fundoToolbarSoja"
      >
    <!-- <v-app-bar-nav-icon></v-app-bar-nav-icon> -->

      <v-row justify="space-between" align="center" elevation="0" tile>
        <v-toolbar-title class="page-title font-weight-bold text-h4 mt-16 ml-5 text-uppercase">{{pageTitle}}</v-toolbar-title>
        <v-card color='light-green darken-3' class="py-2 mx-4 mt-16">
          <v-menu v-for="item in menus" :key="item.text" offset-y router :to="item.to">
            <template #activator="{ on, attrs }">
                <v-btn
                  v-bind="attrs"
                  class="menu-buttons"
                  elevation="0"
                  tile
                  large 
                  text  
                  :to="item.to" 
                  v-on="on" 
                  >
                    {{item.text}}
                  </v-btn>
              </template>
          </v-menu>
        </v-card>
      </v-row>
    </v-toolbar>
  </div>
</template>

<script>
import imgSoja from '~/static/img/img-soja.jpg'

export default {
    data () {
      return {
          fundoToolbarSoja: imgSoja,
          pageTitle: 'International Agro',
          menus: [
            {
              text: 'Home',
              to: '/',
            },
            {
              text: 'Sobre',
              to: '/about',
            },
            {
              text: 'Negócios',
              to: '/bussiness',
            },
            {
              text: 'Contato',
              to: '/contact',
            }
          ]
      }
    }
}
</script>

<style>
  .page-title {
    background-color: #558b2f9d;
  }
  .menu-buttons {
    border-right: 1.5px solid #fff;
  }
</style>