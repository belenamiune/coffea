<template>
        <div class="background_image">
             <img src="../static/images/logo-circulo.svg" width="100px" class="image_resize"> 
           <v-container fluid>
              <v-row>
                  <v-col  :class="`rounded-t-xl`"  class="mt-5 mb-6 pa-20 text-center text-no-wrap white margin justify-center align-center" >
                
                       <v-row>
                            <v-col style="text-align: end">
                            <v-btn
                                icon
                                dark
                                @click="submit"
                                color="secondary"
                                to="login"
                            >
                                <v-icon>mdi-close</v-icon>
                            </v-btn>
                            
                            </v-col>
                       </v-row>
                    
                  
                            <h2> Cuenta confirmada </h2>
                                
                                <v-container>
                                    <v-row>
                                        <v-col cols xs="6">
                                
                                         <p class="text-center mb-8 mt-8">Tu cuenta ha sido confirmada exitosamente </p>
                            
                                        </v-col>
                                    </v-row>
                                </v-container>

                                <img src="../static/images/iconos/check.svg" width="150px"> 
                            <v-container>
                                <v-row>
                                    <v-col>
                                        <v-btn
                                            class="mr-4 mt-6 text-center custom-transform-class text-none"
                                            @click="submit"
                                            color="primary"
                                            rounded
                                            to="/login"
                                        >
                                            
                                            Ingresar
                                        </v-btn>

                                        </v-col>
                                </v-row>
                            </v-container>
                        
                </v-col>
            </v-row>
        </v-container>
                       
    </div>

</template>

<script>
    
  export default {
    
        
        }   

    
    </script>

    <style lang="scss" scoped>

    *  {
          font-family: 'Raleway', sans-serif ;
      }


        .margin{
            position: absolute;
            top: 100px;
            left:0px;
            z-index: 2;
            bottom: 0; 
        }

        .background_image {
            background-image: url('../static/images/background.png');
            background-size: cover;
            padding: 2em;
        }

        .image_resize {
            margin-top: -20px;
        }

         h2 {
            margin-top: 15px;
            font-weight: normal;
        }


        p {

            white-space:pre-wrap !important;
        }

        .v-btn {
            font-weight: normal;
        }        
    </style>