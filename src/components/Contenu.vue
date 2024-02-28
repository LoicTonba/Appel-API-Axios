<template>
  <div class="container mt-5">

    <h1 class="text-center">Appel à une API</h1>
    <img :src="urlImg">
    

  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HContenu',
  data: function(){
    return {
      urlImg: null
    }
  },
 methods: {
    
   
 },
 mounted(){
    axios
     .get(' https://api.thecatapi.com/v1/images/search')
     .then(reponse => {
        console.log(reponse)
        this.urlImg = reponse.data[0].url
     })
 },
  components: {
   
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1{
    margin-top: 100px!important;
  }
  .onglets{
    height: 300px;
  }
</style>
