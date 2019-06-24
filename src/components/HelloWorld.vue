<template>
  <div class="myTodoList">
   <h1>List Tasks</h1>
   
    <SearchBox @searching="searching"></SearchBox>
    <ul>
      <li v-for="x of otherLists" :key="x">{{ x }}</li>
    </ul>
  </div>
</template>

<script>
import SearchBox from './SearchBox';
export default {
  components:{
    'SearchBox':SearchBox,
  },
  data:function(){
    return{
      lists:['imadox','angular'],
      otherLists:[],
      search:'',
    }
    
  },
  created(){
    this.loadData();
  },
  methods:{
    loadData()
    {
     /*  let localS = localStorage.getItem('_items') || []; 
      this.lists = localS; */
          this.otherLists = this.lists;

    },
    searching(search){
       if(search)
       {
         this.otherLists =  this.otherLists.filter(d=>d.indexOf(search) != -1)
         return;
       }
         this.otherLists = this.lists;
       
       
      }
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  lang="scss">
  .myTodoList 
  {
    max-width: 200px;
    margin:0 auto; 
    form{
      input{
        border:0px;
        padding:10px 5px;
        border-bottom:1px solid black;
        outline:0;
      }
    }
    ul{
      list-style: none;
      padding-left:10px;
      li{
        color:#4aca23;
        margin-bottom: 10px;
      }
    }
  }
  
</style>
