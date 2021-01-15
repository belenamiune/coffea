    <template>
        <div class="background_image">
             <img src="../static/images/logo-circulo.svg" width="70px" class="image_resize"> 
           <v-container fluid>
              <v-row>
                  <v-col cols="12" :class="`rounded-t-xl`"  class="mb-4 mt-4 pa-20 text-center text-no-wrap white margin justify-center align-center" >
                
                        <v-btn
                            icon
                            @click="submit"
                            color="secondary"
                            to="bienvenida"
                            >
                                <v-icon>mdi-close</v-icon>
                            </v-btn>

                   <h2> Registrate </h2>

                            <v-text-field
                                v-model="name"
                                :error-messages="nameErrors"
                                label="Nombre de usuario"
                                required
                                class= "mt-4"
                                outlined rounded
                                @input="$v.name.$touch()"
                                @blur="$v.name.$touch()"
                            ></v-text-field>
                                            
                            <v-text-field
                                v-model="email"
                                :error-messages="emailErrors"
                                label="Correo electrónico"
                                class= "mt-4"
                                outlined rounded
                                required
                                @input="$v.email.$touch()"
                                @blur="$v.email.$touch()"
                            ></v-text-field>

                            <v-text-field
                                v-model="password"
                                :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                                :error-messages="passwordErrors"
                                :type="show1 ? 'text' : 'password'"
                                label="Contraseña"
                                hint="Al menos 8 caracteres"
                                class= "mt-4"
                                outlined rounded
                                @input="$v.password.$touch()"
                                @blur="$v.password.$touch()"
                                @click:append="show1 = !show1"
                            ></v-text-field>

                            <v-text-field
                                v-model="passwordConfirmation"
                                :rules="passwordRules"
                                :error-messages="passwordRepitErrors"
                                :append-icon="show ? 'mdi-eye' : 'mdi-eye-off'"
                                :type="show ? 'text' : 'password'"
                                label="Repita la contraseña"
                                hint="Al menos 8 caracteres"
                                class= "mt-4"
                                outlined rounded
                                @click:append="show = !show"
                            ></v-text-field>
                                            
                            <v-checkbox
                            v-model="checkbox"
                            :error-messages="checkboxErrors"
                            label="Acepto los términos y condiciones"
                            required
                            @change="$v.checkbox.$touch()"
                            @blur="$v.checkbox.$touch()"
                            ></v-checkbox>

                            
                            <v-container>
                                <v-row justify="center">
                                    <v-col>
                                        <v-btn
                                            class="mr-4 text-center text-capitalize"
                                            @click="submit"
                                            color="primary"
                                            rounded
                                            to="/codigo_cuenta"
                                        >
                                            
                                            Registrarme
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
        dialog: false,
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
        checkboxErrors () {
            const errors = []
            if (!this.$v.checkbox.$dirty) return errors
            !this.$v.checkbox.checked && errors.push('Debes aceptar los términos y condiciones para continuar')
            return errors
        },
        nameErrors () {
            const errors = []
            if (!this.$v.name.$dirty) return errors
            !this.$v.name.maxLength && errors.push('El nombre de usuario debe tener al menos 6 caracteres')
            !this.$v.name.required && errors.push('Nombre de usuario es obligatorio.')
            return errors
        },
        emailErrors () {
            const errors = []
            if (!this.$v.email.$dirty) return errors
            !this.$v.email.email && errors.push('Ingresa una dirección de correo electrónico válida')
            !this.$v.email.required && errors.push('Correo electrónico es obligatorio')
            return errors
        },

        passwordErrors () {
            const errors = []
            if (!this.$v.password.$dirty) return errors
            !this.$v.password.password && errors.push('La contraseña debe tener al menos 8 caracteres')
            !this.$v.password.required && errors.push('Contraseña es obligatorio')
            return errors
        },

        passwordRepitErrors () {
            const errors = []
            if (!this.$v.passwordConfirmation.$dirty) return errors
            !this.$v.passwordConfirmation.passwordConfirmation && errors.push('La contraseña debe tener al menos 8 caracteres')
            !this.$v.passwordConfirmation.required && errors.push('Contraseña es obligatorio')
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
            top: 70px;
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

        * {
            font-family: 'Raleway', sans-serif;
        }

        
        
    </style>