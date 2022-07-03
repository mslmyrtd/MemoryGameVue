<script setup>

</script>

<template>
  <div class="card">
    <img src="../assets/card-1.jpg" alt="">
  </div>
</template>

<style scoped>
.card{
  width: 200px;
  height:232px;
  border-radius: 5px;
  border:1px solid #666;
   transition: box-shadow .5s;
   margin-left: 15px;
}
.card:hover{
  box-shadow: 0px 5px 48px #666;
  transition: box-shadow .5s;
}
.card:first-child{
  margin-left: 0;
}
</style>
