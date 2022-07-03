<script setup>
import Card from "./Card.vue";
import DefaultCard from "./DefaultCard.vue";
import { ref } from "vue";
const cards = ref([
  { id: 1, component: "app-cards", image: "../src/assets/card-1.jpg" },
  { id: 2, component: "app-cards", image: "../src/assets/card-2.jpg" },
  { id: 3, component: "app-cards", image: "../src/assets/card-3.jpg" },
  { id: 4, component: "app-cards", image: "../src/assets/card-4.jpg" },
  { id: 5, component: "app-cards", image: "../src/assets/card-5.jpg" },
]);
</script>

<template>
  <div class="game-area">
    <h1 class="title">
      <span>Where is the </span>Little Poğaça <strong>?</strong>
    </h1>
    <h4 class="description">
      After selecting one of the open cards, click on the face down card.
    </h4>
    <div class="container">
      <Card v-for="card in cards" :card="card" />
    </div>
    <div class="container">
      <DefaultCard />
    </div>
  </div>
</template>

<style scoped>
.title {
  text-align: center;
  color: rosybrown;
}
.title span {
  color: mediumpurple;
}
.title strong {
  color: darkred;
}
.description {
  color: grey;
  text-align: center;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 50px;
}
</style>
