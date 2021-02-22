<template>
<v-container>
  <navbar />
    <v-row>
        <v-carousel
            cycle
            height="400px"
            hide-delimiter-background
            show-arrows-on-hover
        >
            <v-carousel-item
            v-for="(slides, i) in slides"
            :key="i"
            
            >
            <v-sheet
               height="100%"
            >
                <v-row
                class="fill-height"
                align="center"
                justify="center"
                >
                <div class="carousel_img">
                  <v-img  :src="slides.src" > <div class="carousel_text white--text font-weight-bold rawline" >{{ slides.text }}</div></v-img>
                </div>
                </v-row>
            </v-sheet>
            </v-carousel-item>
        </v-carousel>
    </v-row>

    
   
    <v-row class="mt-5">
        <v-col > 
            <v-list>
                <v-list-item class="px-0">
                                    
                      <v-list-item-content>
                             <v-list-item-title class="black--text  font-weight-semibold ">Las promos más elegidas del mes</v-list-item-title>
                             <v-list-item-subtitle>Date un gusto en la tarde</v-list-item-subtitle>
                        </v-list-item-content>

                </v-list-item>
            </v-list>
        </v-col>
        <v-col  class="mt-7 mr-0">
            <v-btn class="font-weight-semibold primary justify-center align-center  custom-transform-class text-none"  elevation="0" small rounded to="promociones" > 
                         Ver más
                    </v-btn>
                    
        </v-col>
    </v-row>
        <VueSlickCarousel :arrows="true" :dots="true" v-bind="settings" class="mt-0" >
      
      <v-col  cols="11" class="padding" v-for="(promos,i) in promos"  :key="i" ><a :href="promos.to"><v-img  :src="promos.src" max-height="100%" > 
            <div class="informacion"> <div class="white--text font-weight-medium rawline largo" >{{ promos.nombre }}</div> 
            <v-chip class="montserrat"  color="primary">
                {{ promos.precio }}
            </v-chip></div>
      </v-img></a></v-col>
      
     
    </VueSlickCarousel>


    <v-row class="mt-5">
        <v-col > 
            <v-list>
                <v-list-item class="px-0">
                                    
                      <v-list-item-content>
                             <v-list-item-title class="black--text  font-weight-semibold ">¡Canjeá tus puntos!</v-list-item-title>
                             <v-list-item-subtitle>Mirá que productos podes adquirir <br>con tus puntos </v-list-item-subtitle>
                        </v-list-item-content>

                </v-list-item>
            </v-list>
        </v-col>
        <v-col  class="mt-10 mr-0">
            <v-btn class="font-weight-semibold primary justify-center align-center  custom-transform-class text-none"  elevation="0" small rounded to="productos_puntos"> 
                         Ver más
                    </v-btn>
                    
        </v-col>
    </v-row>
        <VueSlickCarousel :arrows="true" :dots="true" v-bind="settings" class="mt-0">
      
      <v-col  cols="11" class="padding"  v-for="(canje,i) in canje"  :key="i"   ><a :href="canje.to"> <v-img  :src="canje.src" max-height="100%"> 
            <div class="informacion"> <div class="   white--text font-weight-bold">{{ canje.nombre }}</div> 
            <v-chip class="montserrat"  color="primary">
                {{ canje.precio }}
            </v-chip></div>
      </v-img></a></v-col>
      
     
    </VueSlickCarousel>

      <v-row class="mt-5">
        <v-col > 
            <v-list>
                <v-list-item class="px-0">
                                    
                      <v-list-item-content>
                             <v-list-item-title class="black--text  font-weight-semibold">Las categorías más consultadas</v-list-item-title>
                             <v-list-item-subtitle>Sugeridos para disfrutar nuevas opciones </v-list-item-subtitle>
                        </v-list-item-content>

                </v-list-item>
            </v-list>
        </v-col>
        <v-col  class="mt-7">
            <v-btn class="font-weight-semibold primary justify-center align-center custom-transform-class text-none"  elevation="0" small rounded to="categorias"> 
                         Ver más
                    </v-btn>
                    
        </v-col>
    </v-row>
        <VueSlickCarousel :arrows="true" :dots="true" v-bind="settings" class="mt-0">
      
      <v-col  cols="11" class="padding"  v-for="(categorias,i) in categorias"  :key="i"  ><a :href="categorias.to"> <v-img  :src="categorias.src" max-height="100%"> 
            <div class=" informacion  white--text font-weight-bold">{{ categorias.nombre }}</div> 
      </v-img> </a></v-col>
      
     
    </VueSlickCarousel>
    
  
    
    </v-container>
</template>

<script>
 import VueSlickCarousel from 'vue-slick-carousel'
 import 'vue-slick-carousel/dist/vue-slick-carousel.css'
  // optional style for arrows & dots
 import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
 import * as firebase from 'firebase/app'
  import 'firebase/auth'
import { getUserFromCookie, getUserFromSession } from '@/helpers'
 

    export default {
      name: 'MyComponent',
        components: { VueSlickCarousel },
        asyncData({ req, redirect }) {
    if (process.server) {
      console.log('server', req.headers)
      const user = getUserFromCookie(req)
      //   console.log('b', getUserFromCookie(req))
      if (!user) {
        console.log('redirecting server')
        redirect('/login')
      }
    } else {
      var user = firebase.auth().currentUser
      if (!user) {
        redirect('/login')
      }
      //   console.log($nuxt.$router)
    }
  },

        data () { 
      return {
        
        slides: [
          {
            src: '/images/home/carousel/slide1-1.png',
            text: 'Pedí tu café por $80',
            
          },
          {
            src: '/images/home/carousel/slide2-2.jpg',
            text: 'Disfruta con amigos',
          },
          {
            src: '/images/home/carousel/slide3.jpg',
            text: 'Promociones increíbles',
            color: 'black',
          },
          
        ],
         
       settings:{
            "dots": true,
            "focusOnSelect": true,
            "infinite": true,
            "speed": 500,
            "slidesToShow": 2,
            "slidesToScroll": 2,
            "touchThreshold": 5,
                },

        promos: [
        {
          src: '/images/home/promos/cafe_nevado.png',
          nombre:'2 Cafés nevados',
          precio:'$170',
          to: '/meriendas_completas'
        },
        {
          src: '/images/home/promos/merienda_completa.png',
          nombre:'2 Meriendas completas',
          precio:'$300',
          to: '/meriendas_completas'
        },
        {
          src: '/images/home/promos/desayuno_americano.png',
          nombre:'Desayuno americano',
          precio:'$200',
          to: '/meriendas_completas'
        },
        {
          src: '/images/home/promos/tailandes.png',
          nombre:'2 Bowls tailandeses',
          precio:'$180',
          to: '/meriendas_completas'
        },
        {
          src: '/images/home/promos/panqueques.png',
          nombre:'Panqueques veggie',
          precio:'$150',
          to: '/meriendas_completas'
        },
        ],

        canje: [
        {
          src: '/images/home/canje/muffins.png',
          nombre:'Muffins',
          precio:'$45',
          to: '/cafe_italiano'
        },
        {
          src: '/images/home/canje/croassint.png',
          nombre:'Croissant',
          precio:'$60',
          to: '/cafe_italiano'
        },
        {
          src: '/images/home/canje/milshakes.png',
          nombre:'Milkshakes',
          precio:'$250',
          to: '/cafe_italiano'
        },
        {
          src: '/images/home/canje/cafe_italiano.png',
          nombre:'Café Italiano',
          precio:'$80',
          to: '/cafe_italiano'
        },
        {
          src: '/images/home/canje/tostado.png',
          nombre:'Tostado veggie',
          precio:'$100',
          to: '/tostado_veggie'
        },
        {
          src: '/images/home/canje/cafe_moca.png',
          nombre:'Café Moca',
          precio:'$90',
          to: '/cafe_italiano'
        },
        
        ],

         categorias: [
        {
          src: '/images/home/categorias/waffles.png',
          nombre:'Waffles',
           to: '/tortas'
        },
         {
          src: '/images/home/categorias/tortas.png',
          nombre:'Tortas',
           to: '/tortas'
        },
         {
          src: '/images/home/categorias/especialidades.png',
          nombre:'Especialidades',
           to: '/tortas'
        },
        {
          src: '/images/home/categorias/sandwiches.png',
          nombre:'Sándwiches',
           to: '/sandwiches'
        },
        {
          src: '/images/home/categorias/jugos.png',
          nombre:'Jugos',
           to:'/sandwiches'
        },
        {
          src: '/images/home/categorias/ensaladas.png',
          nombre:'Ensaladas',
          to: '/sandwiches'
        },
        ],
    }
    }
  
   
    }
</script>

<style lang="scss" scoped>

.rawline{
  font-family: 'rawline', sans-serif !important; 
}

.largo{
  width: 75%;
}

.v-list-item__title{
    font-size: 15px;
    color: black;
}

.v-list-item__subtitle{
    font-size: 13px;
    color: black;
    overflow: visible;
}
.padding{
   height: 100%;
    padding: 0px;
    border-radius: 15px;
    
}


.v-chip.v-size--default{
    border-radius: 10px;
    height: 25px;
    font-size: 18px;
}

.informacion{
    position: absolute;
    bottom: 5%;
    left: 5%;
}

.v-btn{
    position: absolute;
    right: 5%;
}

.slick-dots{
    display: none !important;
}

.carousel_img{
    width: 100%;
    height: auto;
}

.carousel_text{
  margin-top: 70px;
  margin-left: 70px;
  font-size: 24pt;
  width: 50%;
}

*{
  font-family: 'Raleway', sans-serif;  
}

.montserrat{
   font-family: 'rawline', sans-serif !important;  
}


@media screen and (max-width: 320px) {

.carousel_text{
  margin-top: 40px;
  margin-left: 60px;
  font-size: 20pt;
  width: 62%;
}

.v-list-item__title{
    font-size: 13px;
}

.v-list-item__subtitle{
    font-size: 11px;
}

.carousel_img{
    width: 120%;
   
}
}
</style>