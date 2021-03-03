<template>
<div>
<Count :allNewPlan="allNewPlan" :count="count"/> 
<hr/>


<section v-for="(item, index) in  allNewPlan"
      :key="item">
   <i class="fas fa-question-circle"></i>
    <input type="checkbox"  @click="change(item.increase)" v-model="item.increase">

    <p class="text-center" v-bind:class="{completed: item.increase, notcompleted : !item.increase}">{{item.description}}  <a @click="deletePlan(index)" class="float-right">
 <i class="fas fa-trash-alt" id="d" ></i>
 </a></p>

 

  






<div class="input-group mb-3">
  <div class="input-group-prepend">
    <div class="input-group-text">
       <i class="fas fa-edit"></i>
      <input @click="editIt(item.checked, item.description)" v-model="item.checked" type="checkbox">
    </div>
  </div> 
  <input type="text" class="form-control" 
  aria-label="Text input with checkbox"
   @keyup.enter="enterClicked(item.description, index, item, item.checked)" 
   v-model="name"
   placeholder="Edit plan..."
   v-bind:class="{active: !item.checked}">
</div>
<hr/>
     
</section>

     


</div>
</template>


<script>
import Count from './counter.vue'
export default {
    name : 'Plans',

    props :{
    allNewPlan: Array, 
    alert : String,
   
    },

    components:{
    Count
    },
   
    data() {
    return {
    name:'',
    count : 0,
    newPlan: this.allNewPlan,
    
  
    i:'',
   
    
        }
    },


    methods:{

    change(item){ 
      if (item){
        this.count --
      }
      else{
       
        this.count ++
      }
       
     
    },
       

    editIt(item, describe){
      
      this.i = item
       if (item){
        item = false
       
      }
      else{
        item = true
        this.name = describe
       
      }
     
    
    } , 
  
      
    

    enterClicked(value, index){
    
    value = this.name
    this.$emit('message-changed', value, index)
    this.name=''
     
    },

    deletePlan(index) {
    this.allNewPlan.splice(index,1)
      
    if (this.count >=1){
    this.count --
      }

    else if(this.allNewPlan.length < 0) {
    this.allNewPlan = ""
      }
     }

    },
   
    
    }
</script>
<style>
   #p{
   color:#4fc08d;
   font-weight: bold;
  } 
 
  
  #e{
  color:navy
  } 
  #d{
  color: red;
  }

 .active {
  visibility: hidden;
      }
     

  /* .notactive {
  visibility: visible;
      } */
  

  .completed {
  text-decoration: line-through;
  font-weight: bold;
  color:red
}

  .notcompleted {
  color:#4fc08d;
  font-weight: bold
}




 #ul{
  margin: 1rem auto;
  max-width:35rem;
  padding: 1rem; 
 background-color:#4fc08d;
 list-style: none;

 }

#f{
  color: blue;
  font-weight: bold;
}



      
</style>