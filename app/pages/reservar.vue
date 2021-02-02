<template>
    <v-container fluid >
        <navbar />
         <v-row>
        <v-col cols="12" :class="`rounded-t-xl` "  class="pa-16 text-center text-no-wrap primary margin justify-center align-center">
            <v-form v-model ="valid" class="text--white">
                <v-container fluid>
                    <v-row justify="center">
               
                      <v-col
                        cols="6"
                        
                        
                        
                      >

                          <v-text-field
                          v-model="nombre"
                          :rules="nameRules"
                          label="Nombre y apellido"
                          prepend-icon="mdi-border-color"
                          required
                          ></v-text-field>


                          <v-menu
                            ref="menu2"
                            v-model="menu"
                            :close-on-content-click="false"
                            :return-value.sync="date"
                            min-width="290px"
                          >
                          
                          <template v-slot:activator="{ on, attrs }">

                            <v-text-field
                              v-model="date"
                              label="Seleccionar fecha"
                              prepend-icon="mdi-calendar"
                              v-bind="attrs"
                              v-on="on"
                            ></v-text-field>

                          </template>
                          
                          <v-date-picker
                            v-model="date"
                            @input="menu = false"
                            color="secondary"
                           
                          >
                           
                           
                            <v-btn
                              text
                              color="secondary"
                              @click="menu = false"
                              
                            >
                              Cancelar
                            </v-btn>



                          </v-date-picker>
                          
                        </v-menu>

                      </v-col>

                      <v-col
                        cols ="6"
                        xs="12"
                        >
                        

                        <v-menu
                          ref="menu"
                          v-model="menu2"
                          :close-on-content-click="false"
                          :nudge-right="40"
                          :return-value.sync="time"
                          max-width="290px"
                          min-width="290px"
                        >


                        
                          <template v-slot:activator="{ on, attrs }">

                            <v-text-field
                              v-model="time"
                              label="Horario"
                              prepend-icon="mdi-clock-time-four-outline"
                              v-bind="attrs"
                              v-on="on"
                            ></v-text-field>

                          </template>

                          <v-time-picker
                            v-if="menu2"
                            v-model="time"
                            full-width
                            @click:minute="$refs.menu.save(time)"
                            min="9:00"
                            max="21:00"
                            format="24hr"
                            color="secondary"
                            
                          ></v-time-picker>

                        </v-menu>

                        <div>
                        <v-select
                          v-model="personas"
                          :items="cantidad"
                          label="Cantidad de personas"
                          prepend-icon="mdi-account"
                          
                         
                        ></v-select>

                        </div>
                    
                      </v-col>
                
           
                   </v-row>
                   
                </v-container>
              </v-form>
              

                <template>
                    <v-row
                      align="center"
                      justify="space-around"
                    >
                      <v-btn
                        class="mr-4 text-center text-capitalize btn_confirm"
                        rounded
                        color="secondary"
                        to="confirmar_reserva"
                      >
                      
                       Reservar
                      </v-btn>
                    </v-row>
                  </template>
        </v-col>
         </v-row>
    </v-container>

</template>


<script>

export default {
   
    data: () => ({
      date: new Date().toISOString().substr(0, 10),
      menu: false,
      menu2: false,
      personas: '',
       cantidad: [
          '1', '2', '3', '4','5', '6', '7', '8','9', '10', '11','12','13', '14','15', '16', '17', '18','19', '20'
          
        ],
    
    }),

}
</script>



<style>

*  {
       font-family: 'Montserrat', sans-serif !important;
    }

.btn_confirm {
  margin-top: 8em;
}

.margin{
    position:absolute;
    top:200px;
    left:0px;
    z-index:1;
    bottom: 0;
    
}
.v-icon {
  color: white !important;
}

.mdi-cart-outline::before {
  color: #184042 ;
}

.theme--light.v-label {
  color: white !important;
}

.v-input input {
  color: white !important;
}


.mdi-menu::before  {
  
  color: #F8744E;

}

div[role="listbox"] {
  background-color:#F8744E !important;
  color:white !important;

}

.theme--light.v-list-item:not(.v-list-item--active):not(.v-list-item--disabled) {
  color:white !important;
 
}

.theme--light.v-select .v-select__selection--comma {
  color: white !important;
}

@media screen and (max-width: 425px) {
    
  div.col-6 {
    max-width: 100% !important;
    flex: 0 0 100% !important;
    margin: 0;
    padding: 0;
  }

  .btn_confirm {
       margin-top: 6em;
  }

  .margin{
    position:absolute;
    top:100px;
    left:0px;
    z-index:1;
    bottom: 0;
    
  } 

  
  div[role="listbox"] {
    background-color:#F8744E !important;
    color:white !important;
    left: 400px;
    height: 100px;
    top: 400px;
   

}
}


</style>