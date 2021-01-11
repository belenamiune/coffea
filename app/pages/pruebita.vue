<template>

    <v-container  class=" " fluid >

      
            <v-col class="text-right pa-16 mb-10 color font-weight-medium white--text">
                <p>Prueba para ver que sale</p>
            </v-col>
       
            <v-col class="text-right primary pr-13 pt-16">
                <p>Prueba para ver que sale</p>
            </v-col>
       
        
        
            <v-btn dark color="#F8744E"> Aceptar</v-btn>
            <v-btn  color="warning" large :disabled="false"> Aceptar</v-btn>
            <v-btn  color="alert" small> Aceptar</v-btn>
            <v-btn  color="secondary" flat> Sin fondo</v-btn>
       
            <v-btn  color="primary">
                Favorito
                <v-icon right medium>mdi-heart</v-icon>
            </v-btn>
            

            <v-btn  color="primary" outlined>
                Favorito
                <v-icon right medium>mdi-heart</v-icon>
            </v-btn>

            <v-btn  color="primary" outlined rounded>
                Favorito
                <v-icon right medium>mdi-heart</v-icon>
            </v-btn>


        <v-row cols="12" class=" mt-12">

        <v-col  xs="12" sm="4">
            <v-card>
                <v-img src="https://images.pexels.com/photos/5849003/pexels-photo-5849003.jpeg?auto=compress&cs=tinysrgb&dpr=3&h=750&w=1260"   max-height="300"></v-img>
                <v-card-title class="font-weight-bold">
                    Diva en este 2021
                </v-card-title>
                <v-card-text class="text-justify ">
                    <p>Los ocho festivos que se disfrutan a nivel nacional este 2021 son: 1 de enero (viernes, Año Nuevo), 6 de enero (miércoles, Epifanía del señor), 2 de abril (Viernes Santo), 1 de mayo (sábado, Fiesta del Trabajo), 12 de octubre (lunes, Fiesta de la Hispanidad), 6 de diciembre (lunes, día de la Constitución)</p>
                 
                </v-card-text>

                <v-card-actions>
                    <v-btn text color="orange" class="font-weight-semibold"> 
                        Leer más
                    </v-btn>
                </v-card-actions>
            </v-card>
        </v-col>

        <v-col  xs="12" sm="4">
            <v-card>
                <v-img src="https://images.pexels.com/photos/704569/pexels-photo-704569.jpeg?auto=compress&cs=tinysrgb&h=750&w=1260"   max-height="300"></v-img>
                <v-card-title class="font-weight-bold">
                    Esta sale
                </v-card-title>
                <v-card-text class="text-justify ">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus aut nesciunt necessitatibus nulla ut debitis doloremque iste, sunt impedit reprehenderit quae fugiat eius error, tempore delectus eum fugit totam aspernatur!</p>
                 
                </v-card-text>

                <v-card-actions>
                    <v-btn text color="orange" class="font-weight-semibold"> 
                        Ver más
                    </v-btn>
                </v-card-actions>
            </v-card>
        </v-col>

        <v-col  xs="12" sm="4">
            <v-card>
                <v-img src="https://images.pexels.com/photos/302899/pexels-photo-302899.jpeg?auto=compress&cs=tinysrgb&dpr=3&h=750&w=1260"   max-height="300"></v-img>
                <v-card-title class="font-weight-bold">
                    Coffea marzo 2021
                </v-card-title>
                <v-card-text class="text-justify ">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus aut nesciunt necessitatibus nulla ut debitis doloremque iste, sunt impedit reprehenderit quae fugiat eius error, tempore delectus eum fugit totam aspernatur!</p>
                 
                </v-card-text>

                <v-card-actions>
                    <v-btn text color="orange" class="font-weight-semibold" @click="dialog=true"> 
                        Ver más
                    </v-btn>
                </v-card-actions>
            </v-card>
        </v-col>

            <v-dialog v-model="dialog" width="500"  transition="dialog-bottom-transition"  persistent>
                <v-card>
                <v-img src="https://images.pexels.com/photos/4376207/pexels-photo-4376207.jpeg?auto=compress&cs=tinysrgb&h=750&w=1260"   max-height="300"></v-img>
                <v-card-title class="font-weight-bold">
                    Coffea marzo 2021
                </v-card-title>
                <v-card-text class="text-justify ">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus aut nesciunt necessitatibus nulla ut debitis doloremque iste, sunt impedit reprehenderit quae fugiat eius error, tempore delectus eum fugit totam aspernatur!</p> 
                </v-card-text>

                <v-divider></v-divider>
                <v-card-actions>
                    <v-btn text color="orange" class="font-weight-semibold" @click="dialog=false"> 
                        Cerrar
                    </v-btn>
                </v-card-actions>
            </v-card>
            </v-dialog>
            </v-row>
 
            <v-row>
                <v-col >
                     <v-card class="pa-4 ml-0 mb-6" v-for="(item, index) in listaTareas" :key="index">
                <v-img src=""   max-height="300"></v-img>
                <v-chip label color="pink" text-color="white" class="ml-2">
                   <v-icon left>
                        mdi-label
                    </v-icon>
                   {{item.titulo}}
                </v-chip>
                
                <v-card-text class="text-justify" >
                    <p class="ml-n1 mb-0">{{item.descripcion}}</p>
                </v-card-text>

                <v-card-actions class="font-weight-semibold pb-0 pt-0">
                    <v-btn color="warning" @click="editar(index)"> 
                       Editar
                    </v-btn>
                    <v-btn color="error" @click="eliminarTarea(item.id)"> 
                       Eliminar
                    </v-btn>
                </v-card-actions>
            </v-card>
                </v-col>

            <v-col  v-if="formAgregar"> 
                <v-card class="pa-3 mb-3 px-5">
                    <v-form @submit.prevent="agregarTarea">
                        <v-text-field label="Tarea" v-model="titulo"></v-text-field>
                        <v-textarea label="Descripcion" v-model="descripcion"></v-textarea>
                        <v-btn color="green" class="white--text mx-auto" rounded type="submit">Agregar tarea</v-btn>
                    </v-form>
                </v-card>
            </v-col>

            <v-col  v-if="!formAgregar"> 
                <v-card class="pa-3 mb-3 px-5">
                    <v-form @submit.prevent="editarTarea">
                        <v-text-field label="Tarea" v-model="titulo"></v-text-field>
                        <v-textarea label="Descripcion" v-model="descripcion"></v-textarea>
                        <v-btn color="warning" class="white--text mx-auto" rounded type="submit">Editar tarea</v-btn>
                    </v-form>
                </v-card>
            </v-col>

            </v-row>

            <v-snackbar
                v-model="snackbar"
                >
                {{ mensaje}}

                    <v-btn
                    color="pink"
                    text
                    v-bind="attrs"
                    @click="snackbar = false"
                    >
                    Close
                    </v-btn>
                </v-snackbar>
    </v-container>
</template>

<script>
    export default {
        data(){
            return{
                dialog: false,
                listaTareas:[
                    {id: 1, titulo: 'Titulo tarea #1', descripcion: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus aut nesciunt necessitatibus nulla ut debitis doloremque iste.'},
                    {id: 2, titulo: 'Titulo tarea #2', descripcion: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus aut nesciunt necessitatibus nulla ut debitis doloremque iste.'},
                ],
                titulo:'',
                descripcion:'',
                snackbar:false,
                mensaje:'',
                formAgregar:true,
                indexTarea:'',
            }
        },

        methods:{
            agregarTarea(){
               // console.log(this.titulo,this.descripcion);
                if(this.titulo=== ''  || this.descripcion ===''){
                    this.snackbar=true
                    this.mensaje='LLena los espacios vacios'
                } else {
                    this.listaTareas.push({
                        id: Date.now(),
                        titulo: this.titulo,
                        descripcion: this.descripcion,
                    })
                    this.titulo='',
                    this.descripcion='',
                    this.snackbar= true,
                    this.mensaje='tarea agregada'
                    

                }
            },

            eliminarTarea(id){
                this.listaTareas= this.listaTareas.filter(e => e.id != id)
            },

            editar(index){
                 this.formAgregar=false
                 this.titulo= this.listaTareas[index].titulo
                 this.descripcion= this.listaTareas[index].descripcion
                 this.indexTarea= index
            },

            editarTarea(){
                this.listaTareas[this.indexTarea].titulo= this.titulo
                 this.listaTareas[this.indexTarea].descripcion= this.descripcion
                 this.formAgregar=true
                 this.titulo=''
                 this.descripcion=''
            }
        }
  }
    
</script>

<style lang="scss" scoped>
.color{
    background-color:#F8744E;
}

</style>