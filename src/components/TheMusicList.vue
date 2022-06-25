<template>
    <div class="container">
        <div class="row row-cols-6">
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
    name: "TheMusic",
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
                .get(this.apiURL).then((axiosResponse) => {
                this.theMusicList = axiosResponse.data.results;
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