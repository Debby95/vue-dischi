<template>
    <div class="themusic">
        <img class="img-fluid" :src="info.poster" alt="">
        <h5 class="text-white text-uppercase ">{{info.title}}</h5>
        <div class="text-secondary">{{info.author}}</div>
        <div class="text-secondary pb-5">{{info.year}}</div>
    </div>
</template>

<script>
export default {
    name: 'TheMusic',
    props: {
        info: Object,
    },
};
</script>


<style>
    .themusic {
        background-color: #2E3A46;
        text-align: center;
        padding-top: 30px;
        margin-bottom: 20px;
        max-height: 360px;
    }

    .img-fluid {
        width: 200px;
        margin-bottom: 20px;
    }
</style>
