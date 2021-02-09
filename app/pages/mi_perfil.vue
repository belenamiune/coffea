<template >
<v-container fluid>
    <navbar />
    
            <v-col cols="12" :class="`rounded-t-xl` "  class=" text-center text-no-wrap primary margin " >
            
            </v-col>

        <v-row  class="margin_img justify-center align-center ">
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
            
            <v-row class="margin_img justify-center align-center mt-7 white--text"  ><h1 class="font-weight-semibold">Sofía Benza</h1> </v-row>
            
            <v-row>
            <v-form class="margin_img justify-center align-center mt-6">
                <v-container>
                    <v-row>
                       
                        <v-col cols="12">
                             <v-label>Nombre</v-label>
                             <v-text-field
                                label="Sofía Benza"
                                placeholder="Nombre"
                                solo  
                             ></v-text-field>
                            </v-col>

                           <v-col cols="12" class="mt-n6">
                                <v-label>Contraseña</v-label>
                                <v-text-field
                                v-model="password"
                                :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                                :rules="[rules.required, rules.min]"
                                :type="show1 ? 'text' : 'password'"
                                name="input-10-1"
                                solo
                                @click:append="show1 = !show1"
                                ></v-text-field>
                           </v-col>

                            <v-col cols="12" class="mt-n6">
                                <v-label>Correo electrónico</v-label>
                                <v-text-field
                                    label="sofiabenza@gmail.com"
                                    placeholder="Correo electrónico"
                                    solo  
                                ></v-text-field>
                            </v-col>

                            <v-col cols="12" class="mt-n6">
                                <v-label>Teléfono</v-label>
                                <v-text-field
                                    label="03547875621"
                                    placeholder="Teléfono"
                                    solo  
                                ></v-text-field>
                            </v-col>

                            <v-col cols="12" class="mt-n6">
                                <v-label>Barrio</v-label>
                                <v-text-field
                                    label="Rosedal"
                                    placeholder="Barrio"
                                    solo  
                                ></v-text-field>
                            </v-col>

                            <v-col cols="12" class="mt-n6">
                                <v-label>Calle</v-label>
                                <v-text-field
                                    label="Espora"
                                    placeholder="Calle"
                                    solo  
                                ></v-text-field>
                            </v-col>

                            <v-row class="mx-1">
                            <v-col cols="6" class="mt-n6">
                                <v-label>Número</v-label>
                                <v-text-field
                                    label="2053"
                                    placeholder="Número"
                                    solo  
                                ></v-text-field>
                            </v-col>

                            <v-col cols="6" class="mt-n6">
                                <v-label>Piso  <span class="font-weight-thin">(Opcional)</span></v-label>
                                <v-text-field
                                    label=""
                                    placeholder="Piso"
                                    solo  
                                ></v-text-field>
                            </v-col>
                            </v-row>  


                            <v-col cols="12" class="mt-n6">
                                <v-label>Fecha de nacimiento</v-label>
                                <v-row>
                                <v-col cols="1" class="py-5 "><v-icon color="white">mdi-calendar</v-icon></v-col>
                                  <v-col ><v-dialog
                                    ref="dialog"
                                    v-model="modal"
                                    :return-value.sync="date"
                                    width="320px"
                                >
                                    <template v-slot:activator="{ on, attrs } ">
                                        
                                    <v-text-field
                                        v-model="date" 
                                        color="white"
                                        label="2000-01-26"
                                        readonly
                                        v-bind="attrs"
                                        v-on="on"
                                        solo
                                        placeholder="Fecha de nacimiento"
                                    >  </v-text-field>
                                    </template>
                                    <v-date-picker
                                    v-model="date"
                                    scrollable
                                    >
                                    <v-spacer></v-spacer>
                                   <!--  <v-btn
                                        text
                                        color="primary"
                                        @click="modal = false"
                                    >
                                        Cancelar
                                    </v-btn>-->
                                    <v-btn
                                        text
                                        color="primary"
                                        @click="$refs.dialog.save(date)"
                                    >
                                        OK
                                    </v-btn>
                                    </v-date-picker>
                                </v-dialog></v-col></v-row>
                            </v-col> 
                    </v-row>
                </v-container>
            </v-form>
            </v-row>

            <v-row  class=" justify-center align-center primary " >
                    <v-btn class="font-weight-semibold secondary justify-center align-center pa-4 mt-5 mb-10  margin_img margin custom-transform-class text-none" elevation="6" rounded
                    @click="overlay = !overlay" > 
                         Guardar cambios
                    </v-btn>
                    
                   <v-overlay :value="overlay"> 

                       <v-alert
                        v-model="alert"
                        light
                        elevation="2"
                        class="position">
                        <v-icon color="green">mdi-check-circle</v-icon>
                            Los cambios han sido guardados 
                        </v-alert>


                    </v-overlay>
                 </v-row>
           
        

</v-container>
</template>

<script>
export default {
    data () {
        
      
      return {
        overlay: false,
        alert: true,
        show1: false,
        password: 'sofiabenza12345',
        rules: {
          required: value => !!value || 'Required.',
          min: v => v.length >= 8 || 'Min 8 characters',
          
          emailMatch: () => (`The email and password you entered don't match`),

        date: new Date().toISOString().substr(0, 10),
        menu: false,
        modal: false,
        menu2: false,
       },

      } 
    },
     watch: {
        overlay (val) {
        val && setTimeout(() => {
             this.overlay = false;},2000);
       
      

        }
        },   
  }
  

  
</script>

<style lang="scss" scoped>
.margin{
    position:absolute;
    top:200px;
    left:0px;
    bottom:0;
    height: 90%;
    padding-bottom: 0;
    z-index:1;
  
}

.margin_img{
    position: relative;;
    top:80px;
    bottom: 0;
    z-index:2;}

h1{
    font-size: 22px;
  
}

.theme--light.v-label{
    color: white;
}

.v-text-field {
    border-radius:15px;
}

.v-label{
    padding-left: 8px;
}

.v-alert:not(.v-sheet--tile) {
     border-radius: 30px;
}

.position{
    position: relative;
    top: -350px;
    right: 0;
}

*{
  font-family: 'rawline', sans-serif !important; 
  overflow: visible;
}

.montserrat{
  font-family: 'Montserrat', sans-serif;
}
</style>