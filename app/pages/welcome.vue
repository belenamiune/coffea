<template>
  <v-app>
    <!--- OPEN NAVBAR !--->
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

              </v-navigation-drawer>

              <v-app-bar
                :clipped-left="clipped"
                fixed
                app
              >
              <v-app-bar-nav-icon 
              @click.stop="drawer = !drawer" 
              color="#F8744E"/>
                
              </v-app-bar>
            
            <!--- CLOSE NAVBAR !--->

              <v-main>
                <v-container>
                   <v-row>
                      <v-col>
              
                        </v-col>
                    </v-row>
                 </v-container>
            </v-main>
    
    </v-app>

</template>


<script>

  export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-home',
          title: 'Inicio',
          to: '/'
        },
        {
          icon: 'mdi-account',
          title: 'Mi cuenta',
          to: '/register_form'
        },
        {
          icon: 'mdi-cart-outline',
          title: 'Productos',
          to: ''
        },
        {
          icon: 'mdi-calendar',
          title: 'Reservas',
          to: ''
        },
        {
          icon: 'mdi-store',
          title: 'Sucursales',
          to: ''
        },
        {
          icon: 'mdi-logout',
          title: 'Cerrar sesión',
          to: ''
        },
      ],

      miniVariant: false,
      right: true,
      rightDrawer: false,
    }
  }

    
  }
</script>

<style scoped>

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

  
</style>

