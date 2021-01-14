<template>
        <div class="background_image">
             <img src="../static/images/logo-circulo.svg" width="100px" class="image_resize"> 
           <v-container fluid>
              <v-row>  
                  <v-col :class="`rounded-t-xl`"  class="mt-5 mb-6 pa-27 text-center text-no-wrap white margin justify-center align-center" >
                       
                    <v-btn
                        icon
                        dark
                        @click="submit"
                        color="secondary"
                        to="bienvenida"
                     >
                    
                        <v-icon>mdi-close</v-icon>
                    </v-btn>


                    
                    <h2> Ingresá </h2>
                        <v-text-field
                            v-model="name"
                            label="Nombre de usuario"
                            required
                            class= "mt-4"
                            outlined rounded
                            @input="$v.name.$touch()"
                            @blur="$v.name.$touch()"
                        ></v-text-field>

                        <v-text-field
                            v-model="password"
                            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                            :type="show1 ? 'text' : 'password'"
                            label="Contraseña"
                            class= "mt-4"
                            outlined rounded
                            @input="$v.password.$touch()"
                            @blur="$v.password.$touch()"
                            @click:append="show1 = !show1"
                        ></v-text-field>

                            <a href="/olvidar_contraseña"> <p class="text-right" style="color: gray; font-size: 13px"> ¿Olvidaste tu contraseña? </p> </a>

                                <div class="text-center mb-8 mt-8">
                                    <h4> Inicia sesión con: </h4>
                                    <div class="mt-5 mb-6">
                                            <a href="/home"> <img src="../static/images/iconos/google.png" class="mr-5"> </a>
                                        
                                            <a href="/home"> <img src="../static/images/iconos/facebook.png"> </a>
                                        </div>
                                </div>

                            <v-container>
                                <v-row justify="center">
                                    <v-col>
                                        <v-btn
                                            class="mr-4 text-center text-capitalize"
                                                @click="submit"
                                                color="primary"
                                                rounded
                                                to="sucursales"
                                        >
                                                
                                                Iniciar sesión
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
    import { validationMixin } from 'vuelidate'
    import { required, maxLength, minLength,  email, sameAs } from 'vuelidate/lib/validators'

  export default {
    mixins: [validationMixin],

    validations: {
      name: { required },
      email: { required, email },
      password: { required },
      passwordConfirmation: { required }, 
      select: { required },
      checkbox: {
        checked (val) {
          return val
        },
      },
    },

    data() {
    return {
        name: '',
        email: '',
        password: '',
        passwordConfirmation: '',
        checkbox: false,
        show1: false,
        show2: true,
        show3: false,
        show4: false,
        password: '',
        value: null,
        show: false,
        dialog1: false,
        dialog2: false,
        title: 'Escriba la nueva contraseña',
        update: 'Repita la contraseña',
        isFormValid: true,
        passwordRules: [
        password => !!password || 'Contraseña es obligatorio.',
        password => password.length >= 8 || 'Al menos 8 caracteres',
        confirmation => confirmation === this.password || 'Las contraseñas ingresadas no coinciden'
        ]


    }
},

    computed: {
      nameErrors () {
        const errors = []
        if (!this.$v.name.$dirty) return errors
        !this.$v.name.maxLength && errors.push('El nombre de usuario debe tener al menos 6 caracteres')
        !this.$v.name.required && errors.push('Nombre de usuario es obligatorio.')
        return errors
      },

       passwordErrors () {
        const errors = []
        if (!this.$v.password.$dirty) return errors
        !this.$v.password.password && errors.push('La contraseña debe tener al menos 8 caracteres')
        !this.$v.password.required && errors.push('Contraseña es obligatorio')
        return errors
      },

     
    },

    methods: {
      submit () {
        this.$v.$touch()
        
      },
    },

    
  }
    </script>

    <style lang="scss" scoped>

        .margin{
            position: absolute;
            top: 100px;
            left:0px;
            z-index: 2;
            bottom: 0; 
        }
        
        
        .background_image{
            background-image: url('../static/images/background.png');
            background-size: cover;
            padding: 2em;
        }

        .image_resize {
            margin-top: -20px;
            
        }

        * {
            font-family: 'Raleway', sans-serif;;
        }


        a {
            text-decoration: none;
            
        }

        a::before {
            color: red
        }
        
        h2 {
            margin-top: 15px;
            font-weight: normal;
        }

        h4 {
            font-weight: normal;
        }

        
        
                
    </style>