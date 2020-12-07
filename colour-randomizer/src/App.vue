<template>
<body v-bind:style="{ backgroundColor: actual_color }">
   <div id="app">
    <nav class="navbar navbar-dark bg-dark" >
      <a class="navbar-brand" href="#">
        <img src="./assets/balde.png" width="30" height="30" class="d-inline-block align-top" alt="" loading="lazy">
          {{this.actual_color}}
      </a>
    </nav>
  </div>
</body>
 
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      hex:['0','1','2','3','4','5','6','7','8','9','a','b','c','d','e','f'],
      actual_color: 'test',
    }
  },
  components: {
    
  },
  methods :{
    getColor(){
      var num = 0
      var code = '#'
      while(num <= 5){
        code +=  this.hex[this.getRandomIntInclusive(0,13)]
        num += 1
     }
      this.actual_color = code
      return this.actual_color



    },
    getRandomIntInclusive(min, max) {
    min = Math.ceil(min);
    max = Math.floor(max);
    return Math.floor(Math.random() * (max - min + 1)) + min;
    }
    
},
created(){
      this.getColor()
    }

}
</script>

<style>

body, html{
  height: 100%;
}
.colour{
  
  height: 100%;
  width: 250px;
 }
</style>
