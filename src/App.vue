<script setup>
import GameCards from "@/components/GameCards.vue";
import Celebrate from "@/components/Celebrate.vue";
import Failure from "@/components/Failure.vue";
import { shallowRef } from "vue";
const activeComponent = shallowRef(GameCards);
</script>

<template>
  <component :is="activeComponent"></component>
</template>

<style>
body {
  font-family: sans-serif;
}
</style>
