<template>
    <v-container>
        <navbar />
            <v-row class="mt-8">
                <v-col cols="12" justify="center">
                     <h2 class="text-center  mb-15"> Reserva confirmada </h2>
                     <p class="text-center mb-5"> Tu reserva ha sido 
                confirmada exitosamente
                     </p>
                    
                    <div class="text-center mt-15">
                      <img src="../static/images/check.svg" width="150px"> 
                    </div>

                    <template>
                    <v-row
                      align="center"
                      justify="space-around"
                    >
                      <v-btn
                        class="mr-4 text-center text-capitalize btn_confirm"
                        rounded
                        color="secondary"
                        to="mis_reservas"
                      >
                      
                        Ver mis reservas
                      </v-btn>
                    </v-row>
                  </template>
                </v-col>
            </v-row>
    </v-container>
</template>

<script>
export default {
    
}
</script>

<style>



.btn_confirm {
    margin-top: 7em;
}

</style>