<template>
    <div>
       Card
       <div v-if="loading">loading card...</div>
        <div v-else>cid: {{cid}} </div>
       
    </div>
</template>

<script>
export default {
    data() {
        return{
            cid:0,  
            loading:true
        }
    },
    watch:{//뷰 라우트 변경 감지
        '$route': {
            handler: 'fetchData',
            immediate: true,
        }
    },
    methods:{
        fetchData(){
            this.loading = true
            setTimeout(() => {
                 this.cid = (this.$route.params.cid)
                 this.loading = false
            }, 500);
        }
    }    
}
</script>

<style>

</style>