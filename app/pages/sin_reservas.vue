<template>
   <v-container>

       <v-row class="justify-center align-center mt-3">
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

       <v-row class="justify-center align-center mt-7"><h1 class="font-weight-semibold">Sofía Benza</h1> </v-row>
       

                <v-row  class="justify-center align-center text-center ma-5" >
                    <v-alert text color="secondary" class=" margin">
                         <p>Todavía no se ha registrado ninguna reserva</p>
                    </v-alert>
                </v-row>
                <v-row  class="justify-center align-center text-center" >
                    <v-btn class="font-weight-semibold primary justify-center align-center pa-4 mt-12 text-capitalize " elevation="6" rounded to="reservas"> 
                         Reservar
                    </v-btn>

                 </v-row>

   </v-container>
</template>

<script>

export default {
    
}

</script>

<style lang="scss" scoped>

.theme--light.v-expansion-panels .v-expansion-panel-header .v-expansion-panel-header__icon .v-icon {
    color:white;
   bottom: 1px;
}


button.v-expansion-panel-header--active{
      background-color:none !important;
      border-style: solid;
     border-color: #F8744E;
     border-radius:10px;
     margin: 0;
  }

.v-list-item{
    padding: 0;
}

.v-list-item__title{
    font-size: 13px;
    color: black;
    
}

h1{
    font-size: 22px;
    color: black;
}

.col{
    color: black;
}

.v-dialog > .v-card > .v-card__title {
    word-break: normal; 
    font-size: 18px;
}


*{
  font-family: 'rawline', sans-serif !important; 
  color: black;
}

.montserrat{
  font-family: 'Montserrat', sans-serif;
}

.margin{
    margin-top:50px;
}
</style>