<template>

    <v-container  fluid >
        <v-row>
            <v-col cols="12" :class="`rounded-t-xl` "  class="pa-6 text-center text-no-wrap primary margin justify-center align-center" >
            
                <v-avatar  color="secondary" class="mt-16" size="62">
                    <span class="white--text headline font-weight-bold ">600 </span>
                </v-avatar>
        

                <v-row class="secondary--text justify-center align-center text-center mt-8">

                    <h2 >PUNTOS DISPONIBLES</h2>
                </v-row>

                <v-btn class="font-weight-semibold secondary text-capitalize margin_puntos " elevation="0" rounded> 
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



.margin_img{
    margin-top: -620px;
} 

.margin{
    margin-top: 300px;
}

.margin_puntos{
    margin-top: 180px;
}

div.container{
    padding: 0;
}


//.v-btn{
//    font-size: 16px;
//}
</style>