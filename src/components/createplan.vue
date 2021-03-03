<template>
<div>
 
<div class="input-group mb-3" id="app">
  <input type="text"
   v-model="plan" 
  class="form-control" 
  placeholder="Add a plan..." 
  aria-label="Add a plan..." 
  aria-describedby="basic-addon2">
  <div class="input-group-append">
    <button class="btn"  @click="addPlan" type="button"> <strong><i class="fas fa-plus"></i> </strong></button>
  </div>
</div>


<Plans  v-bind:class="{display : !dis}"    :alert="alert" :allNewPlan="allNewPlan" :description="allNewPlan.description" v-on:message-changed="messageChanged"/>


</div>
</template>






<script>
 import Plans from './plans.vue'
 export default {
 name:'Create',
 components:{
 Plans
    },
   
 data() {
 return {
 plan: '' ,
 newPlan:'',
 allNewPlan : [],
 i:'',
alert: 'My Plans',
display:true,
dis: false

    }
 },

methods:{
addPlan(){
if(this.plan == ''){
alert('Please add a plan..')

}else{
this.newPlan =   {description:this.plan, checked:false, increase:false}
this.allNewPlan.push(this.newPlan)
this.plan = ''
            
}
 
 this.dis = true
            
},

messageChanged(value, index){
this.i = index
if(value == ''){
alert('oti yawere')
} else{
this.allNewPlan[this.i].description = value
}
}
},
}
</script>



<style >
 .display{
    visibility: hidden;
 } 
 
</style>