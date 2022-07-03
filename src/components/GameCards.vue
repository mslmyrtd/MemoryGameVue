<script setup>
import Card from './Card.vue';
import DefaultCard from './DefaultCard.vue';
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
      <Card v-for="card in 5"/>
    </div>
    <div class="container">
      <DefaultCard/>
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
