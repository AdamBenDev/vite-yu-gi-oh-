<template>
  <div>
    <h1>yu-gi-oh</h1>
  </div>
</template>

<script>
import axios from 'axios'
  export default {
    data(){
      return {
        API_URL: "https://db.ygoprodeck.com/api/v7/cardinfo.php",
        cards: null
      }
    },
    methods: {
      callApi(url){
        axios
        .get(url)
        .then(Response => {
          console.log(Response);
        })
        .catch(err => {
          console.log(err);
          console.error(err.message);
        })
      }
    },
    mounted(){
      this.callApi(this.API_URL);
    }
  }
</script>

<style lang="scss" scoped>

</style>