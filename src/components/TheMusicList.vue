<template>
    <div class="container">
        <select class="mt-3" v-model="selected">
            <option v-for="genre in getGenreList" :key="genre">
                {{genre}}
            </option>
        </select>
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
    },
    computed: {
        getGenreList() {
            const list = [];
            this.theMusicList.forEach((theMusic) => {
                if (!list.includes(theMusic.genre)) {
                    list.push(theMusic.genre);
                }
            });
            return list;
        },
    },
};
</script>

<style>
    select {
        border-radius: 30px;
        width: 100px;
        text-align: center;
    }
</style>