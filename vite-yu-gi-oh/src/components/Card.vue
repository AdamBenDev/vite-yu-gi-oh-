<template>
    <div class="card">
      <img :src="card.card_images[0].image_url" alt="card image">
      <div class="card-info">
        <h2>{{ card.name }}</h2>
        <p><strong>Attribute:</strong> {{ card.attribute }}</p>
        <p><strong>Level:</strong> {{ card.level }}</p>
        <p><strong>Type:</strong> {{ card.type }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Card',
    props: {
      card: Object,
    },
  };
  </script>
  
  <style scoped>
  .card {
    margin: 10px;
    border: 1px solid #ccc;
    box-shadow: 2px 2px #eee;
    border-radius: 4px;
    overflow: hidden;
    width: 200px;
  }
  
  .card img {
    width: 100%;
  }
  
  .card-info {
    padding: 10px;
  }
  </style>