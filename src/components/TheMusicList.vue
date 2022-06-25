<template>
    <div class="container">
        <div class="row row-cols-5 pt-5">
            <div class="col" v-for="theMusic in theMusicList" :key="theMusic.author">
                <TheMusic :info="theMusic"></TheMusic>
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";
import TheMusic from "./TheMusic.vue";


export default {
    name: "TheMusicList",
    components: {TheMusic},
    props: {
        info: Object,
    },
    data() {
        return {
            apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
            theMusicList: [],
            loading: true,
        };
    },
    methods: {
        fetchTheMusicList() {
            axios
                .get(this.apiURL).then((resp) => {
                //this.theMusicList = response.data.results;
                this.theMusicList = resp.data.response
                
            });
        },
    },
    mounted() {
        this.fetchTheMusicList();
    }
};
</script>

<style>
</style>