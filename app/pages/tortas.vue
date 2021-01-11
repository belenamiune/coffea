<template>
    <v-container>
      <navbar />
        <v-row justify="center" class="text-center">

          <div class="text-left">
              <v-chip
                class="ma-2"
                color="primary"
                text-color="white"
                :to="'/categories'"
              >
        
                  Categorías
              </v-chip>

                    <p style="color: orange; font-weigth: 800; display:inline; margin-left: 0 !important"> /  </p>
             
              <v-chip
                class="ma-2"
                color="primary"
                text-color="white"
                :to="'/categories'"
              >
                  {{ header }}
              </v-chip>
            </div>

        <v-col
          v-for="(producto, i) in productos"
          :key="i"
          cols="12"
          class="text-center"
        >
          
          <v-card :to="producto.to"> 
            <div class="d-flex flex-no-wrap">
              <div>

                <v-avatar
                class="ml-2 mt-2 mb-3"
                size="160"
                tile
              >
                <v-img :src="require(`../static/images/productos/tortas/${producto.image}`)" max-width="135px"></v-img>
              </v-avatar>

              </div>
             
              <div class="title-style">
                <v-card-title
                  class="headline text-left"
                  v-text="producto.title"
                ></v-card-title>

                <v-card-subtitle>{{ producto.description }}</v-card-subtitle>

              

               
                <v-rating
                  :value="producto.star"
                  color="primary"
                  dense
                  half-increments
                  readonly
                  size="14"
                ></v-rating>

               
                 <p class="grey--text">{{producto.comments}} </p>
                
                
                
               </div>

              
                  
               </div>


               <v-row justify="end">
                <h2><span style="color: #F8744E">$</span>{{producto.precio}}</h2>
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
      header: 'Tortas',
      productos: [
        {
          image: 'marquise.png',
          title: 'Marquise de chocolate',
          description: 'Brownie con frutos rojos y crema chantilli',
          star: 3,
          comments: '(110)',
          precio: '100',
          to:'cafe_italiano'
         
        },
        {
          image: 'volcan.png',
          title: 'Torta volcán',
          description: 'Volcán de chocolate con dulce de leche',
          star: 4,
          comments: '(385)',
          precio: '120',
          to:'cafe_italiano'
        },
        {
          image: 'tarta_frutilla.png',
          title: 'Tarta de frutillas',
          description: 'Tarta de frutillas con crema chantilly ',
          star: 5,
          comments: '(330)',
          precio: '95',
          to:'cafe_italiano'
        },
        {
          image: 'oreo.png',
          title: 'Torta oreo',
          description: 'Torta con dulce de leche, oreo y chocolate',
          star: 5,
          comments: '(300)',
          precio: '200',
          to:'cafe_italiano'
        },
        {
          image: 'tiramisu.png',
          title: 'Tiramisú',
          description: 'Postre italiano con café, licor y vainillas',
          star: 5,
          comments: '(140)',
          precio: '190',
          to:'cafe_italiano'
        },
       
      ],
    }),
  }
</script>

<style scoped>
.v-card__title  {
  font-size: 16px !important;
}

.v-card__subtitle {
  text-align: center !important;
  font-size: 13px;
}

.v-avatar {
  justify-content: initial;
}

.v-rating, p{
  text-align: left;
  margin-left: 1em !important;
 
}

p {
  font-size: 14px;
}

h2 {
  margin-right: 3em;
}





 @media screen and (min-width: 320px) {
    

    .v-card__subtitle {
      text-align: left !important;
    }

    .title-style {
      margin-left: -1.5em !important;
    }

    h2 {
      margin-right: 1em !important;
      margin-top: -1em !important;
    }

    .v-rating {
       margin-top: -1em;
}


 }

</style>