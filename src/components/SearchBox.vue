<template>
    <div>
       <form>
        <input type="text" v-model="search" @keyup="searching()"/>
         </form>
    </div>
</template>
<script>
export default {
    data(){
        return{
            search:'',
        };
    },
    created(){

    },
    methods:{
        searching(){
            this.$emit('searching',this.search);
        },
        loading(){

        }
    }
}
</script>
