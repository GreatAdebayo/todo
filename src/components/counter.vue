<template >
   
       <p  id="c" class="text-center">  {{ count }} of {{allNewPlan.length}} Completed </p> 
  
</template>

 <script> 
export default {
   name:'Count' ,
   props:{
   allNewPlan :Array,
   count : Number
   }
}
</script>

<style >
   #c {
   font-size: 13px;
   color: #4fc08d;
   font-weight: bold;
  
    
   } 
   p{
    color: #4fc08d;
   }
</style>