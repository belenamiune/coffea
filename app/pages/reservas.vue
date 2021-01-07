<template>
    <v-container  fluid >
        <navbar />
        <v-row>
            <v-col cols="12" :class="`rounded-t-xl` "  class="pa-16 text-center text-no-wrap primary justify-center align-center margin " > </v-col>

            <v-carousel :show-arrows="false">

                <v-carousel-item>
                    <v-row class="mx-auto margin_img justify-center" >
                        
                        <v-img src="/images/carrousel1.svg" max-width="300" ></v-img>
                       
                    </v-row>

                    <v-row class="justify-center" >
                       
                        <p class="p1"> Elegí la sucursal en donde 
       quieras reservar tu lugar </p>

                    </v-row>
                </v-carousel-item>

                  <v-carousel-item>
                    <v-row class="mx-auto margin_img2 justify-center" >
                           
                            <v-img src="/images/carrousel2.svg" max-width="350" height="200"></v-img>

                    </v-row>

                    <v-row class="justify-center" >
                       
                        <p class="p2"> Ingresá la hora, dia, mes y la cantidad
        de personas que estarán ese dia  </p>

                    </v-row>
                </v-carousel-item>

                  <v-carousel-item>
                    <v-row class="mx-auto margin_img3 justify-center" >
                       
                        <v-img src="/images/carrousel3.svg" max-width="300"  ></v-img>

                    </v-row>

                     <v-row class="justify-center" >
                       
                        <p class="p3"> Seguí los pasos para 
     confirmar tu reserva  </p>

                    </v-row>
                </v-carousel-item>

           </v-carousel>

           


           
        </v-row>   
                <v-row justify="center">
                    <v-btn 
                    class="font-weight-semibold secondary text-capitalize text-center margin_button" 
                    rounded
                    to="/sucursales"> 
                        Reservá tu mesa
                    </v-btn>
                </v-row>
    </v-container>

</template>

<script>

    export default {
    
        
    }
</script>


<style>

   * {
       font-family: 'Raleway', sans-serif;
   }

    .margin {
        position:absolute;
        top:200px;
        left:0px;
        z-index:1;
        bottom: 0;
        
    }

    .margin_img{
        position:relative;
        top:60px;
        z-index: 3;

    }

    .margin_img2 {
        position:relative;
        top:80px;
        z-index: 3;
    }

    .margin_img3 {
        position:relative;
        top: 30px;
        z-index: 3;
    }


    div.container {
        padding: 0;
    }

    .v-carousel {
        position:relative;
        top:50px;
        z-index: 3;

    }

    div.v-carousel__controls {
        background-color: transparent !important;    
    
    }

    .v-carousel__controls > .v-item-group {
        margin-top: -2em;
        color: white;
    }

    .v-btn {
        color: white;
        font-weight: lighter;
        z-index: 3;
    }

    p {
        color: white;
        z-index: 3;
        white-space: pre-wrap !important;
        font-weight: normal;
        line-height: 25px;
        
    }

    .p1 {
        margin-top: 7em;
    
        
    }

    .p2 {
        margin-top: 10em;
    }

    .p3 {
        margin-top: 5em;
    }

    @media screen and (min-width: 1024px) {
    .margin_button {
        margin-top: 3em;
    }

    }

     @media screen and (min-width: 320px) {
    .margin_button {
        margin-top: 5em;
    }

    }



</style>