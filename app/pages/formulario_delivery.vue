<template>
   <v-container fluid>
          <toolbar />
            <v-col cols="12" :class="`rounded-t-xl` "  class="text-center text-no-wrap primary margin " > </v-col>

            <v-row  class="margin_img justify-center align-center delivery">
                <v-col class="text-center justify-center">
               <img src="../static/images/delivery.png" class="delivery">
                </v-col>
            </v-row>
            
            
            <v-row>
                <v-form class="margin_img justify-center align-center mt-6">
                    <v-container>
                            <v-row>
                                <v-col cols="12" class="mt-n6">
                                    <v-label>Barrio</v-label>
                                        <v-select
                                            v-model="select"
                                            :hint="`${select.state}`"
                                            :items="items"
                                            item-text="state"
                                            label="Rosedal"
                                            persistent-hint
                                            return-object
                                            single-line
                                            solo
                                            ></v-select>
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

                           </v-row>
            </v-container>
        </v-form>
    </v-row>

            <v-row  class=" justify-center align-center primary " >
                <v-btn 
                class="font-weight-semibold secondary justify-center align-center pa-4 mt-5 mb-10  margin_img margin custom-transform-class text-none" 
                elevation="6" 
                rounded
                to=""
                > 
                        Confirmar
                </v-btn>
                    
            
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
        select: { state: 'Rosedal'},
        items: [
                { state: 'Alberdi'},
                { state: 'Crisol'},
                { state: 'General Paz'},
                { state: 'Juan B Justo'},
                { state: 'Parque'},
        ],
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

* {
    font-family: 'Raleway', sans-serif;
}
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
    top:30px;
    bottom: 0;
    z-index:2;
}

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

.delivery { 
    max-width: 250px !important;
    margin-left: 0.5em;
}

</style>