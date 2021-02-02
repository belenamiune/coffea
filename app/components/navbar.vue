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
                      <v-list-item-subtitle>800 puntos</v-list-item-subtitle>
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
                                              <v-btn  class="font-weight-semibold boton pa-4 text-capitalize"  elevation="6" rounded @click="dialog=false"> 
                                                  Cancelar
                                              </v-btn>
                                              <v-btn class="font-weight-semibold primary pa-4 text-capitalize" elevation="6" rounded @click="dialog=false" to="/"> 
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

                
        
                          <v-tab>
                              <v-badge
                                color="primary"
                                content="6"
                                bottom
                              
                              >
                                <v-icon> mdi-cart-outline </v-icon>
                              </v-badge>
                            </v-tab>
                          

              
                           <v-chip 
                              color="secondary"
                              text-color="white"
                              to="/mi_cuenta"
                             >
                              <v-avatar
                                left
                                class="secondary darken-4"
                              >
                                <v-img src="https://randomuser.me/api/portraits/women/26.jpg"></v-img>
                              </v-avatar>

                              <div>
                                    <p> Mis puntos </p> 
                                    <span> 800 </span> 
                              </div>
                              
                            </v-chip>
               
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
          to: '/mis_reservas'
        },
        {
          icon: 'mdi-store',
          title: 'Sucursales',
          to: '/sucursales'
        },
      ]
     
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
   font-family: 'Montserrat', sans-serif;
 }

    #app {
        background-color: red;
        font-family:  'Raleway', sans-serif;

    }

    .v-list-item__title {
        color: #FDF7F7;
    }

    .v-list-item__subtitle {
      color: #FDF7F7 !important;
      font-family:  'Montserrat', sans-serif;
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


</style>