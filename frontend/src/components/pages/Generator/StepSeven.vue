<template>
    <v-container>
        <v-row>
            <v-col>
                All done! Please download your original spatial audio.
            </v-col>
        </v-row>
        <v-row>
            <v-col>
                <v-btn
                    id='downloadButton'
                    color='#AFB42B'
                    :href='audioURL'
                    download
                >
                    <v-icon>mdi-download</v-icon>download
                </v-btn>
            </v-col>
        </v-row>
        <v-row>
            <v-col>
                <v-btn
                    color='#26A69A'
                    @click='continueStep'
                >Back to Step1
                </v-btn>
            </v-col>
        </v-row>
    </v-container>
</template>
<script>
import { library } from '../library.js'
export default{
    data: () => ({
        library,
    }),
    props:['spaceName','audioURL'],
    methods:{
        continueStep(){
            this.$emit('change-step', 1);
        },
    },
    mounted(){
        const downloadButton = document.getElementById('downloadButton');
        downloadButton.setAttribute('download', 'convoluted.wav');
    }
}
</script>
