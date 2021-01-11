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
                <v-img :src="require(`../static/images/productos/sandwiches/${producto.image}`)" max-width="135px"></v-img>
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
      header: 'Sándwiches',
      productos: [
        {
          image: 'pavo.png',
          title: 'Sándwich de pavo',
          description: 'Pan casero con pavo caramelizado',
          star: 3,
          comments: '(102)',
          precio: '80',
          to:'cafe_italiano'
         
        },
        {
          image: 'veggie.png',
          title: 'Tostado veggie',
          description: 'Tostado con palta, tomate y queso',
          star: 5,
          comments: '(230)',
          precio: '100',
          to:'cafe_italiano'
        },
        {
          image: 'tostado.png',
          title: 'Tostado jamón y queso',
          description: 'Tostado de jamón, queso y tomate (opcional)',
          star: 4,
          comments: '(300)',
          precio: '90',
          to:'cafe_italiano'
        },
        {
          image: 'bondiola.png',
          title: 'Sándwich de bondiola',
          description: 'Pan casero con bondiola desmenuzada y mayonesa casera',
          star: 5,
          comments: '(100)',
          precio: '180',
          to:'cafe_italiano'
        },
        {
          image: 'ternera.png',
          title: 'Sándwich de ternera',
          description: 'Pan casero con ternera a la cerveza negra',
          star: 4,
          comments: '(225)',
          precio: '120',
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