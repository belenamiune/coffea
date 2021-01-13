<template>
  <v-card flat>
    <v-container fluid>
      <v-row class="child-flex">
        <div>
          <v-toolbar>
            <v-btn
              icon
            >
              <v-icon color="accent">mdi-arrow-left</v-icon>
            </v-btn>

            <v-toolbar-title></v-toolbar-title>

            <v-spacer></v-spacer>
           

                    <v-btn
                        icon
                        color="secondary"
                        class="search_icon"
                      >
                        <v-icon>mdi-magnify</v-icon>
                      </v-btn>

                  <div> 
                    <v-tab>

                      <v-badge
                        color="primary"
                        content="6"
                        bottom
                        class="cart_icon"
                      >
                        <v-icon> mdi-cart-outline </v-icon>
                      </v-badge>

                    </v-tab>

                  </div>
                
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
               
          
             </v-toolbar>
           </div>
         </v-row>
      </v-container>
  </v-card>
</template>

<script>
export default {
  data () {
    return  {
     
    }
      }

}
</script>

<style scoped>


    .v-badge__badge {
      inset: calc(80% - 4px) auto auto calc(100% - 4px);
    }

    span {
      font-weight: 900;
      padding-left: 1em !important;
      
    }

    p {
      margin-bottom: 0 !important;
      margin-top: 0.5em !important;
    }

    .theme--light.v-chip:not(.v-chip--active) {
      height: 40px;
    }

    .v-tab.v-tab {
      padding: 0 !important

    }

    .search_icon {
      margin-right: 1em;
    }

     @media screen and (min-width: 320px) {
    
      .theme--light.v-chip:not(.v-chip--active) {
         margin-left: -2em;
    } 

    .cart_icon {
      margin-left: -3em;
    }

    .search_icon {
      margin-right: -1em;
    }

    }

</style>


