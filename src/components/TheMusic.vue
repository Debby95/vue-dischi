<template>
    <div class="themusic">
        <img class="img-fluid" :src="info.poster" alt="">
        <h5>{{info.title}}</h5>
        <div>{{info.author}}</div>
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
</style>
