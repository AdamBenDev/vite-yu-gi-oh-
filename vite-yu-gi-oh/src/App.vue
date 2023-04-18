<template>
  <div>
    <h1>yu-gi-oh</h1>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        API_URL: "https://ygoprodeck.com/api-guide/",
        cards: null
      }
    },
    methods: {
      callApi(){
        
      }
    }
    mounted(){
      this.callApi(this.API_URL);
    }
  }
</script>

<style lang="scss" scoped>

</style>