<template>
    <v-container fluid>
        <navbar />

       <v-row class="justify-center align-center mt-16">
           <v-avatar size="205" color="#EFEFEF">
            <v-avatar size="190" color="primary">
                <v-avatar size="180" color="#EFEFEF">
                        <v-avatar size="150">
                                    <img src="https://randomuser.me/api/portraits/women/26.jpg">
                        </v-avatar>
                </v-avatar>
            </v-avatar>
           </v-avatar>
       </v-row>

       <v-row class=" justify-center align-center mt-7"><h1 class="font-weight-semibold">Sofía Benza</h1> </v-row>

        <v-row class=" justify-center align-center mt-7 ">

             <v-btn class="font-weight-regular  custom-transform-class text-none black--text" elevation="4" x-large to="mis_puntos"> 
                 
                  <v-img src="/images/iconos/puntos.svg" max-width="27" class="mr-3 ml-n2" ></v-img>   
                   Mis puntos                                
             </v-btn>
             
        </v-row>

         <v-row class=" justify-center  mt-7 ">

             <v-btn class="font-weight-regular  custom-transform-class text-none black--text" elevation="4" x-large to="mis_pedidos"> 
                  <v-img src="/images/iconos/carrito-pedidos.svg" max-width="25" class="mr-4 " ></v-img>   
                   Mis pedidos                                
             </v-btn>
             
        </v-row>


        <v-row class=" justify-center mt-7 ">

             <v-btn class="font-weight-regular custom-transform-class text-none black--text" elevation="4" x-large to="mis_reservas"> 
                  <v-img src="/images/iconos/reserva.svg" max-width="25" class="mr-3  ml-3" ></v-img>   
                   Mis reservas                             
             </v-btn>
             
        </v-row>

        
        
        <v-row class=" justify-center  mt-7 ">

             <v-btn class="font-weight-regular custom-transform-class text-none black--text" elevation="4" x-large to="mi_perfil"> 
                  <v-img src="/images/iconos/personas.svg" max-width="25"  class="mr-3 ml-n7" ></v-img>   
                   Mi perfil                             
             </v-btn>
             
        </v-row>
        

   </v-container>
   
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
h1{
    font-size: 22px;
    color: black;
}


.v-btn:not(.v-btn--round).v-size--x-large{
    background-color: white;
    border-color: red;
    border-radius:10px;
    width: 80%;
}

v-img{
    position: absolute;
    left: 50px;
}

*{
  font-family: 'rawline', sans-serif !important; 
  color: black;
}

.montserrat{
  font-family: 'Montserrat', sans-serif;
}
</style>