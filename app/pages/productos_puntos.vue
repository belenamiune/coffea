<template>
    <v-container>
      <navbar />
        <v-row justify="center" class="text-center">

              <v-chip
                class="ma-2"
                color="primary"
                text-color="white"
                :to="'/categorias'"
              >
                  {{ header }}
              </v-chip>
            

        <v-col
          v-for="(producto, i) in productos"
          :key="i"
          cols="12"
          class="text-center"
        >
          
          <v-card :to="producto.to"> 
            <div class="d-flex flex-no-wrap">
              <div>
                
                <v-row>
                  <v-col cols="4">
                      <v-avatar
                      class="mt-2 mb-2"
                      size="160"
                      tile
                    >
                      <v-img :src="require(`../static/images/productos/canje_puntos/${producto.image}`)" max-height="120px" max-width="130px"></v-img>
                    </v-avatar>
                  </v-col>

                  <v-col cols="8">
   
                      <v-card-title
                        class="headline"
                        v-text="producto.title"
                      ></v-card-title>

                      <v-card-subtitle>{{ producto.description }}</v-card-subtitle>
                      <v-rating
                        :value="producto.star"
                        color="primary"
                        dense
                        half-increments
                        readonly
                        size="10"
                      ></v-rating>

               
                         <p class="grey--text solo-numeros">{{producto.comments}} </p>
                    </v-col>
                </v-row>

                        <div>
                 
                
                 </div>
              </div>
                 
               </div>


               <v-row justify="end">
                <h2 class="solo-numeros"><span style="color: #F8744E">$</span>{{producto.precio}}</h2>
               </v-row>
          </v-card>
            
        
        </v-col>
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
        font-family: 'Raleway', sans-serif;
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
}

.solo-numeros {
    font-family: 'Montserrat', sans-serif;
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
      margin-right: 1em !important;
      margin-top: -1em !important;
    }

    .v-rating {
       margin-top: -1em;
       padding: 0 !important;
       margin-left: -2.3em !important;
    }

    p {
      text-align: left;
      margin-left: 1em !important;
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

 }

</style>