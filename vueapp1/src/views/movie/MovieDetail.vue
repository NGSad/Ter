<template>
    <h1>{{detail.tatle}}</h1>
    <p>{{detail.summary}}</p>
</template>

<script>
    import axios from "axios";
    export default {
        data(){
            return{
                detail:{}
            }
        },
        created(){
            let url=`https://bird.ioliu.cn/v2?url=https://api.douban.com/v2/movie/subject/${
                this.$route.params.movieId
                }`;
            axios.get(url).then(res =>{
                this.detail = res.data;
            });
        }
    };
</script>

<style lang="scss" scoped>

</style>