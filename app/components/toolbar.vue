<template>
 
    <v-container fluid>
      <v-row class="child-flex">
        <div>
          <v-toolbar  dense fixed >
            <v-btn
              icon
               onClick="history.go(-1);"
            >
              <v-icon color="accent">mdi-arrow-left</v-icon>
            </v-btn>

           

            <v-spacer></v-spacer>
                    <v-btn
                        icon
                        color="secondary"
                        class="search_icon"
                        @click="dialog = true"
                      >
                        <v-icon>mdi-magnify</v-icon>
                      </v-btn>

                   <!--  <template v-slot:activator="{ on, attrs } ">-->
                       <v-dialog v-model="dialog" width="500"  transition="dialog-top-transition"  class="dialogo mx-0"  overflow-hidden full-screen >
                             
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
           <!--   </template> -->

                  
                    <v-tab to="carrito" class="carrito">

                      <v-badge
                        color="primary"
                        content="3"
                        overlap
                        bottom
                        class="cart_icon font-weight-bold" 
                      >
                        <v-icon style="color: #184042 !important" class="color_cart_outside"> mdi-cart-outline </v-icon>
                      </v-badge>
                    </v-tab>
                  

                  <v-card elevation="0" color="secondary" class="puntos mr-n3">
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
                          @click="toMyAccount()"
                          
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
                    
               
          
             </v-toolbar>
           </div>
         </v-row>
      </v-container>
 
</template>

<script>
export default {
data() {
    return {
        dialog: false,
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
        ]
    };
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

  methods:{
    
      toMyAccount () {
           
                 window.location.href = 'mi_cuenta';     
                
        },
    } 
}

</script>

<style scoped>

    * {
      font-family: 'rawline', sans-serif !important; 
    }

  .v-toolbar__content {
      padding-left: 0px !important; 
    }
    .v-badge__badge {
      inset: calc(80% - 8px) auto  calc(80% - 8px) !important;
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
      padding: 0 !important;
      
    }
 
    .carrito{
      min-width: 70px !important;
    }
    
    div.container{
        padding: 0;
    }

    .search_icon {
      margin-right: 1em;
    }

    span {
      font-weight: normal;
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

    
    .puntos{
        border-radius: 20px 10px 10px 20px ;
        width: 35%;
        height: 90%;
        margin-right: 1px !important;
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

   .v-application a {
     color:black !important;
     
   }

   .miavatar {
     margin-left: 0.5em !important;
   }

@media screen and (min-width: 375px){
td {
      width: 300px !important;
      padding-top: 8px;
    }

    
    
    .puntos{
        border-radius: 20px 10px 10px 20px ;
        width: 30%;
        height: 90%;
        margin-right: 1px !important;
    }

}

@media screen and (min-height: 644px){

  
  .v-dialog > .v-card{
        height: 80% !important;
    }


}
</style>


