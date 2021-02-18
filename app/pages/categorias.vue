<template>
    <v-container>
        <navbar />
        
            <v-row>
                <v-col cols="6" class="text-center mt-4">
                    <a href="/cafe"><img src="../static/images/categorias/cafe.png"></a>
                </v-col>
                <v-col cols="6" class="text-center mt-4">
                    <a href="/jugos"><img src="../static/images/categorias/jugos.png"></a>
                </v-col>
              <v-col cols="6" class="text-center" >
                    <a href="/sandwiches"><img src="../static/images/categorias/sandwiches.png"></a>
                </v-col>
                <v-col cols="6" class="text-center">
                    <a href="/tortas"><img src="../static/images/categorias/tortas.png"></a>
                </v-col>
                <v-col cols="6" class="text-center">
                    <a href="/ensaladas"><img src="../static/images/categorias/ensaladas.png"></a>
                </v-col>
                <v-col cols="6" class="text-center">
                    <a href="/waffles"><img src="../static/images/categorias/waffles.png"></a>
                </v-col>
                <v-col cols="6" class="text-center">
                    <a href="/muffins"><img src="../static/images/categorias/muffins.png"></a>
                </v-col>
                <v-col cols="6" class="text-center">
                    <a href="/especialidades"><img src="../static/images/categorias/especialidades.png"></a>
                </v-col>
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
img {
  max-width: 138px !important;
  margin-left: 0 !important;
}

.col-6 {
  padding-left: 5px;
 
  
}


</style>