<template>
    <v-row>
        <v-col>
            <div class="google-maps">
                <iframe src="https://www.google.com/maps/d/embed?mid=19cpKP-0Lc8VHjYAyrHyU2V_b_kB3f8ac" 
                    width="1800" 
                    height="350" 
                    frameborder="0" 
                    style="border:0;" 
                    allowfullscreen="" 
                    aria-hidden="false" 
                    tabindex="0">
                </iframe>

            </div>
        </v-col>
    </v-row>
</template>


<script>
export default {
    data() {
    }
}


</script>

<style lang="css">

.google-maps iframe {
        position: absolute;
        top: 0;
        left: 0;
       
    }


</style>