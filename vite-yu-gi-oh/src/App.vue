<template>
  <div>
    <h1>Yu-Gi-Oh Cards</h1>
    <div v-if="isLoading" class="loader"></div>
    <div class="card-container">
      <Card v-for="(card, index) in cards" :key="index" :card="card"></Card>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import Card from './components/Card.vue';

export default {
  name: 'App',
  components: {
    Card,
  },
  data() {
    return {
      apiEndpoint: 'https://db.ygoprodeck.com/api/v7/cardinfo.php',
      cards: [],
      isLoading: true,
    };
  },
  methods: {
    getCards() {
      axios.get(this.apiEndpoint).then((response) => {
        this.cards = response.data.data.slice(0, 15);
        this.isLoading = false;
      });
    },
  },
  mounted() {
    this.getCards();
  },
};
</script>

<style>
.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.loader {
  border: 16px solid #f3f3f3;
  border-top: 16px solid #3498db;
  border-radius: 50%;
  width: 120px;
  height: 120px;
  animation: spin 2s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>