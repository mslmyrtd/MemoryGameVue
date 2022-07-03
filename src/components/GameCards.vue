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
const selectedCard = ref(null);
const answer = ref({});
let k = Math.ceil(Math.random() * cards.value.length);
answer.value = cards[k - 1];
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
      <transition-group   name="rotate-all" appear>
        <Card
        :key="card.id"
          v-for="card in cards"
          :card="card"
          @click="selectedCard = card.id"
          :class="{ shadow: selectedCard == card.id }"
        />
     </transition-group>
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
  flex-wrap: wrap;
}
.shadow {
  box-shadow: 0px 5px 48px #38969f !important;
  transition: box-shadow 0.5s;
}
/* Animation */

.rotate-all-enter-active{
 animation: rotate-all ease-in-out 2s forwards;
}
.rotate-all-leave{}
.rotate-all-leave-active{}
@keyframes rotate-all{
from {
transform: rotateY(0);
}
to{
transform: rotateY(1080deg);
}
}
</style>
