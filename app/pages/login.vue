<template>
        <div class="background_image">
             <img src="../static/images/logo-circulo.svg" width="100px" class="image_resize"> 
           <v-container fluid>
              <v-row>  
                  <v-col :class="`rounded-t-xl`"  class="mt-5 mb-6 pa-27 text-center text-no-wrap white margin justify-center align-center" >
                       
                        <v-row>
                            <v-col style="text-align: end">
                                <v-btn
                                    icon
                                    dark
                                    @click="submit"
                                    color="secondary"
                                    to="bienvenida"
                                >
                                
                                    <v-icon>mdi-close</v-icon>
                                </v-btn>

                            </v-col>
                        </v-row>


                <div class="login">
                    <h2> Ingresá </h2>
                    <v-form  @submit.prevent="pressed">
                         <div class="login">
                                 <v-text-field
                                    v-model="email"
                                    label="Nombre de usuario"
                                    type="email"
                                    required
                                    class= "mt-4"
                                    outlined rounded
                                    @input="$v.name.$touch()"
                                    @blur="$v.name.$touch()"
                                ></v-text-field>
                            </div>
                            <div class="password">
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
                            </div>
                    
            

                            <a href="/olvidar_contraseña"> <p class="text-right" style="color: gray; font-size: 13px"> ¿Olvidaste tu contraseña? </p> </a>

                                <div class="text-center mb-8 mt-8">
                                    <h4> Inicia sesión con: </h4>
                                    <div class="mt-5 mb-6">
                                            <a @click="googleSignIn"> <img src="../static/images/iconos/google.png" class="mr-5"> </a>
                                        
                                            <a href="/home"> <img src="../static/images/iconos/facebook.png"> </a>
                                        </div>
                                </div>
                            <button>
                               <v-btn
                                            class="mr-4 text-center text-capitalize"
                                                color="primary"
                                                rounded
                                        >
                                                
                                                Iniciar sesión
                                </v-btn>

                            </button>

            
                     </v-form>

                     
                            <div class="error" v-if="error">{{error.message}}</div>
                        </div>
                
                              
                             
                        
                </v-col>
            </v-row>
        </v-container>
                       
    </div>

</template>

<script>
    import { validationMixin } from 'vuelidate'
    import { required, maxLength, minLength,  email, sameAs } from 'vuelidate/lib/validators'
    import * as firebase from 'firebase/app'
    import 'firebase/auth'

  export default {
    mixins: [validationMixin],

    validations: {
      email: { required, email },
      password: { required },
    },

    data() {
    return {
        name: '',
        email: '',
        password: '',
        error: '',
    }
},


    methods: {
      pressed() {
      firebase
        .auth()
        .signInWithEmailAndPassword(this.email, this.password)
        .then(data => {
          console.log(data)
          this.$router.replace({ name: 'home' })
        })
        .catch(error => {
          this.error = error
        })
    }, 
     googleSignIn () {
        this.provider = new firebase.auth.GoogleAuthProvider()
        firebase.auth().signInWithPopup(this.provider).then(result => {
          // store the user ore wathever
          this.$router.push('/home')
        }).catch(e => {
          this.$snotify.error(e.message)
          console.log(e)
        })
      }
    },

    
  }
    </script>

    <style lang="scss" scoped>

        * {
            font-family: 'Raleway', sans-serif;
        }

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