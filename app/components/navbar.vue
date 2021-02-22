<template>
    <v-card>
      
        <v-navigation-drawer
                v-model="drawer"
                :mini-variant="miniVariant"
                :clipped="clipped"
                fixed
                app
                color="secondary"
        >

              <template v-slot:prepend>
                  <v-list-item two-line>
                    <v-list-item-avatar>
                      <img src="https://randomuser.me/api/portraits/women/26.jpg">
                    </v-list-item-avatar>

                    <v-list-item-content>
                      <v-list-item-title>Sofía Benza</v-list-item-title>
                      <v-list-item-subtitle>200 puntos</v-list-item-subtitle>
                    </v-list-item-content>
                  </v-list-item>
                </template>

                <v-divider color ="#FDF7F7"></v-divider>

                <v-list>
                  <v-list-item
                    v-for="(item, i) in items"
                    :key="i"
                    :to="item.to"
                    router
                    exact>

                    <v-list-item-action>

                      <v-icon 
                      color="#FDF7F7"> 
                      {{ item.icon }}
                      </v-icon>

                    </v-list-item-action >

                    <v-list-item-content 
                      color="red"
                      >
                      <v-list-item-title 
                      v-text="item.title" 
                      />

                    </v-list-item-content>
                  </v-list-item>
                </v-list>

                <v-list class="logout" exact>
                  <v-list-item>

                    <v-list-item-action>

                      <v-icon 
                        color="#FDF7F7"> 
                        mdi-logout
                        </v-icon>

                    </v-list-item-action>

                    <v-list-item-content>
                         <v-list-item-title class="font-weight-semibold" @click="dialog=true, overlay = !overlay">  
                               Cerrar sesión
                         </v-list-item-title>


                         <v-dialog v-model="dialog" width="500"  transition="dialog-bottom-transition"  persistent>
                                <v-card >
                                    <v-img  src="/images/cerrar_sesion.png" ></v-img>
                                        <v-card-title class="font-weight-regular justify-center align-center text-center pt-0" >
                                          ¿Estás seguro de cerrar sesión?
                                        </v-card-title>
                                
                                        <v-card-actions class=" justify-center align-center pb-6 pt-0">
                                              <v-btn  class="font-weight-semibold boton pa-4 custom-transform-class text-none"  elevation="6" rounded @click="dialog=false"> 
                                                  Cancelar
                                              </v-btn>
                                              <v-btn class="font-weight-semibold primary pa-4 custom-transform-class text-none" elevation="6" rounded @click="dialog=false" to="/login"> 
                                                  Cerrar sesión
                                              </v-btn>

                                        </v-card-actions>
                                </v-card>
                           </v-dialog>

                    </v-list-item-content>
                  </v-list-item>
                </v-list>

            </v-navigation-drawer>

                <v-app-bar
                  :clipped-left="clipped"
                  fixed
                  app
                  dense
                  
                >
                <v-app-bar-nav-icon 
                  @click.stop="drawer = !drawer" 
                  color="#F8744E"
                />
                <v-spacer></v-spacer>

                  <v-btn
                        icon
                        color="secondary"
                        class="search_icon"
                        @click="dialog2 = true"
                      >
                        <v-icon style="margin-left: 2.5em !important">mdi-magnify</v-icon>
                      </v-btn>

                   <!--  <template v-slot:activator="{ on, attrs } ">-->
                       <v-dialog v-model="dialog2" width="500"  transition="dialog-top-transition"  class="dialogo mx-0"  overflow-hidden full-screen >
                             
                              <v-card class=" justify-center align-center text-center">

                                  <div class="row">
                                      <div class="search-wrapper panel-heading col-sm-12 mr-5 ml-5 mt-5 mb-3">
                                              <input class="form-control input_busqueda" type="text" v-model="searchQuery" placeholder="Búsqueda" />
                                        </div>
                                 </div>
                                      
                                 <div class="row" style="margin-left: 2.5em">
                                      <div>
                                        <table v-if="resources.length" class="table">
                                            <tbody>
                                                <tr v-for="item in resultQuery">
                                                    <td>
                                                      <v-avatar 
                                                        size="32" 
                                                        color="primary" 
                                                        class="miavatar">
                                                        <v-img :src="require(`../static/images/categorias/${item.icon}`)"
                                                        > 
                                                        </v-img>
                                                        
                                                      </v-avatar>
                                                        <a class="pt-1" v-bind:href="item.uri"  target="_self">{{item.title}}</a></td>
                                                </tr>
                                            </tbody>
                                        </table>
                                    </div>
                                 </div>

                              </v-card>

                            </v-dialog>  

                
        
                          <v-tab to="carrito">
                              <v-badge
                                color="primary"
                                content="3"
                                class="font-weight-bold "
                                overlap
                                bottom
                              
                              >
                                <v-icon style="color: #184042 !important" class="color_cart_outside"> mdi-cart-outline </v-icon>
                              </v-badge>
                            </v-tab>
                          

              
                       <v-card elevation="0" color="secondary" class="puntos " style="margin-right:10px !important;">
                          <v-row class="mt-1">
                            <v-div
                              text-color="white"
                              to="/mi_cuenta"
                            >
                              <v-avatar
                                left
                                class="secondary darken-4  "
                                size="44"
                                color="white"
                                style="margin-right:5px; margin-top:-4px;"
                              >
                              
                              <v-img src="https://randomuser.me/api/portraits/women/26.jpg"></v-img>

                              </v-avatar>
                           </v-div>

                            <v-div class="text-center white--text" >

                              <v-col cols="12" style="padding:0;" >
                                <h6 style="margin-top:2px; font-weight: 400;"> Mis puntos </h6> 
                              </v-col>

                              <v-col cols="12" style="padding:0;" >
                                <h4 class="mt-n1" style=" font-weight: 500 !important;"> 200 </h4> 
                              </v-col>

                            </v-div>
                        </v-row>
                      </v-card> 
               
                </v-app-bar>
        </v-card>
</template>

<script>
   export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      dialog: false,
      overlay: false,
      dialog2: false,
      searchQuery: null,
        resources:[
            {title:"Promociones",uri:"/promociones",category:"d",icon: 'cafe.png'},
            {title:"Especialidades",uri:"/especialidades",category:"d",icon: 'especialidades.png'},
            {title:"Café", uri:"/cafe", category:"a", icon: 'cafe.png'},
            {title:"Jugos",uri:"/jugos",category:"a",icon: 'jugos.png'},
            {title:"Sándwiches",uri:"/sandwiches",category:"a",icon: 'sandwiches.png'},
            {title:"Tortas",uri:"/tortas",category:"b",icon: 'tortas.png'},
            {title:"Ensaladas",uri:"/ensaladas",category:"b",icon: 'ensaladas.png'},
            {title:"Waffles",uri:"/waffles",category:"b",icon: 'waffles.png'},
            {title:"Muffins",uri:"/muffins",category:"c",icon: 'muffins.png'},
        ],
      items: [
        {
          icon: 'mdi-home',
          title: 'Inicio',
          to: '/home'
        },
        {
          icon: 'mdi-account',
          title: 'Mi cuenta',
          to: '/mi_cuenta'
        },
        {
          icon: 'mdi-cart-outline',
          title: 'Productos',
          to: '/categorias'
        },
        {
          icon: 'mdi-calendar',
          title: 'Reservas',
          to: '/reservas'
        },
        {
          icon: 'mdi-store',
          title: 'Sucursales',
          to: '/sucursales_menu'
        },
      ]
     
    }
    
  },
  computed: {
    resultQuery(){
      if(this.searchQuery){
      return this.resources.filter((item)=>{
        return this.searchQuery.toLowerCase().split(' ').every(v => item.title.toLowerCase().includes(v))
      })
      }else{
        return this.resources;
      }
    }
  },
    
     watch: {
      overlay (val) {
        val && setTimeout(() => {
          this.overlay = false
        }, 2000)
      },
    },
    

  }
</script>

<style lang="scss" scoped>

 * {
    font-family: 'rawline', sans-serif !important; 
 }

 .numeros{
   font-family: 'Montserrat', sans-serif;
 }

    #app {
        background-color: red;
    }

    .v-list-item__title {
        color: #FDF7F7;
    }

    .v-list-item__subtitle {
      color: #FDF7F7 !important;
      font-weight: lighter;
    }

    .v-list-item__content {
      color: white;
    }

    .v-card__title {
      word-break: normal; 
    }

    .logout {
      margin-top: -0.8em;
    }

    .v-badge__badge {
      inset: calc(80% - 8px) auto auto calc(100% - 4px);
    }

    span {
      font-weight: normal;
      padding-left: 1em !important;
      
    }

    p {
      margin-bottom: 0 !important;
      margin-top: 0.5em !important;
    }

    .theme--light.v-chip:not(.v-chip--active) {
      height: 40px;
    }

    .input_busqueda {
      border: 1px solid lightgray;
      border-radius: 20em;
      width: 90%;
      height: 40px;
    }

    td {
      text-align: left;
      width: 250px;
      border-radius: 20px;
      height: 40px;
      padding-top: 8px;
      /*border: 1px solid #184042;*/
    }

    table {
      border-collapse: separate;
      border-spacing: 5px;
    }

    a {
      text-decoration: none;
      padding: 1em;
    }

    ::placeholder {
      padding: 1em;
    }

   tr {
     width: 230px;
     border-radius: 8px;
     background-color: #eeecec;
     
   }

   
  .v-dialog > .v-card{
        border-radius: 0px 0px 30px 30px;
        position: absolute;
        left:0;
        top: 0;
        right: 0;
        height: 65%;
    }

  .v-dialog > .v-card > .v-card__title {
        word-break: normal; 
        font-size: 20px;
    }

  .v-card__actions > .v-btn.v-btn{
        width: 80%;
        border-radius: 10px;
        height: 45px;
  }


@media screen and (min-width: 320px) {
    
    

    
    .puntos{
        border-radius: 20px 10px 10px 20px !important;
        width: 35%;
        height: 90%;
        margin-right: 1px !important;
    }

}

@media screen and (min-width: 375px){

    .puntos{
        border-radius: 20px 10px 10px 20px ;
        width: 30%;
        height: 90%;
        margin-right: 1px !important;
    }

}
</style>