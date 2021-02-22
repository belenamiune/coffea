<template>
    <v-container>
      <toolbar />
        <v-row justify="center" class="text-center">

          <v-row class="sin_margin justify-center align-center text-center">
             
          </v-row>
        <v-row class="mt-8">
        <v-col
          v-for="(producto, i) in productos"
          :key="i"
          cols="12"
          class="text-center"
        >
          
          <v-card :to="producto.to" class=" ma-1 color_card" elevation="0"> 
            <div class="d-flex flex-no-wrap">
              <div>
                
                <v-row>
                  <v-col cols="4">
                      <v-avatar
                      class="mt-2 mb-2"
                      size="160"
                      tile
                    >
                      <v-img :src="require(`../static/images/productos/canje_puntos/${producto.image}`)" class="imagen_promo"></v-img>
                    </v-avatar>
                  </v-col>

                  <v-col cols="8">
   
                      <v-card-title
                        class="headline black--text"
                        v-text="producto.title"
                      ></v-card-title>

                      <v-card-subtitle class="black--text">{{ producto.description }}</v-card-subtitle>
                       <v-row>
                        <v-col cols="6">
                            <v-rating
                              :value="producto.star"
                              color="primary"
                              dense
                              half-increments
                              readonly
                              size="12"
                            ></v-rating>
                          </v-col>

                          <v-col cols="6">
                            <p class="black--text solo-numeros">{{producto.comments}} </p>
                          </v-col>

                      </v-row>

                      <v-card-text class="justify-end">
                            <h2 class="text-right" style="font-size:24px;"><span style="color: #F8744E" >$</span>{{producto.precio}}</h2>
                     </v-card-text>
                    </v-col>
                </v-row>

                       
              </div>
                 
               </div>


               
          </v-card>
            
        
        </v-col>
        </v-row>
      </v-row>
    </v-container>

</template>


<script>
import Navbar from '../components/navbar.vue'
  export default {
    data: () => ({
      header: 'Canje de puntos',
      productos: [
        {
          image: 'italiano.png',
          title: 'Café Italiano',
          description: 'Café negro con leche descremada',
          star: 4,
          comments: '(165)',
          precio: '80',
          to:'cafe_italiano'
         
        },
        {
          image: 'moca.png',
          title: 'Café Moca',
          description: 'Café con leche montada y chocolate',
          star: 4,
          comments: '(325)',
          precio: '90',
          to:'cafe_italiano'
        },
        {
          image: 'veggie.png',
          title: 'Tostado veggie',
          description: 'Tostado con palta, tomate y queso',
          star: 5,
          comments: '(230)',
          precio: '100',
          to:'tostado_veggie'
        },
        {
          image: 'bondiola.png',
          title: 'Sándwich de bondiola',
          description: 'Pan casero con bondiola desmenuzada y mayonesa casera',
          star: 5,
          comments: '(100)',
          precio: '180',
          to:'tostado_veggie'
        },
        {
          image: 'oreo.png',
          title: 'Torta oreo',
          description: 'Torta con dulce de leche, oreo y chocolate',
          star: 5,
          comments: '(300)',
          precio: '200',
          to:'torta_oreo'
        },
       
      ],
    }),
  }
</script>

<style scoped>

* {
       font-family: 'rawline', sans-serif !important;  
    }

.v-card__title  {
  font-size: 16px !important;
}

.v-card__subtitle {
  text-align: center !important;
  font-size: 13px;
}

.v-avatar {
  justify-content: initial;
  margin-left: 2em !important;
}


p {
  font-size: 14px;
}

h2 {
  margin-right: 3em;
}

.v-rating {
    max-width: 65% !important;
     margin-left: 1em !important;
}

.solo-numeros {
   margin-top: -10px;
}
 
.color_card{
    background-color:#EFEFEF !important;  
}

.v-sheet.v-card{
    border-radius:10px;
}

 @media screen and (min-width: 320px) {
    
    
    .v-card__subtitle {
      text-align: left !important;
    }

    .v-card__title {
      word-break: normal;
      text-align: left;
    }

    h2 {
      margin-right: 0em !important;
      margin-top: -0.5em !important;
    }

    .v-rating {
       margin-top: -1em;
       padding: 0 !important;
       
    }

    p {
      text-align: left;
      margin-left: 0em !important;
      margin-right: 1em !important;
    }

    .col-8 {
      padding-left: 2em !important;
    }

    .v-avatar {
      margin-left: 0 !important;
    }

    .v-rating {
       max-width: 100% !important;
    }

.imagen_promo{
    max-height: 120px !important;
    max-width: 120px !important;
    margin-left: 10px !important;
  }
 }

</style>