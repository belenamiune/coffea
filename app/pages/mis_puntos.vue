<template>

    <v-container  fluid >
        <toolbar />
        <v-row>
            <v-col cols="12" :class="`rounded-t-xl` "  class="pa-16 text-center text-no-wrap primary margin justify-center align-center" >
            
                <v-avatar  color="secondary" class="mt-16 montserrat" size="62">
                    <span class="white--text headline font-weight-bold ">200 </span>
                </v-avatar>
        

                <v-row class="secondary--text justify-center align-center text-center mt-8">

                    <h2 >PUNTOS DISPONIBLES</h2>
                </v-row>

                <v-btn class="font-weight-semibold secondary custom-transform-class text-none margin_puntos btn_style " elevation="0" rounded to="productos_puntos"> 
                  Canjear puntos
                </v-btn>

            </v-col>
            <v-row class=" mx-auto margin_img justify-center" >
                <v-img src="/images/mis_puntos.png" max-width="300"  height="230" ></v-img>
            </v-row>
            
            
        </v-row>

        
    </v-container>

 
   
</template>

<script>
export default {
     data(){
    
        return {}
    }
}
</script>

<style lang="scss" scoped>


.margin{
    position:absolute;
    top:200px;
    left:0px;
    z-index:1;
    bottom: 0;
    
}

.margin_img{
    position:relative;
    top:80px;
    z-index:2;}

.margin_puntos{
    margin-top: 180px;
}

div.container{
    padding: 0;
}

*{
  font-family: 'rawline', sans-serif !important; 
  
}

.montserrat{
  font-family: 'Montserrat', sans-serif;
}

@media screen and (min-height: 644px){

  
  .btn_style{
        margin-top: 7em !important;
    }


}

</style>