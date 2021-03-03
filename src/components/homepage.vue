<template>
<div id="app">
<header> <strong><i class="far fa-sticky-note"></i> {{title}}</strong> </header>
<Create/>
</div>
</template>

<script>


import Create from './createplan.vue'

export default {
  name: 'Home',
  components : {
  Create
    },

  props:{
  title: String
  }
  }

</script>



<style>
* {
  box-sizing: border-box;
}

html {
  font-family: 'Jost', sans-serif;
}

body {
  margin: 0;
}

header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #4fc08d;
  color: white;
  text-align: center;
  width: 90%;
  max-width: 40rem;
  font-size: 1.5rem;
}
#app {
  margin: 1rem auto;
  max-width:35rem;
  padding: 0.8rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
 
}



#app button {
background-color: #4fc08d;
color: white
}

</style>
