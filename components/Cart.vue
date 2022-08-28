<template>
    <div class="StorePage">
    <CardsList @add="add" @del="del" />
    <div class="footer">
      <p class="nav">navigation</p>
      <!-- <p class="cart">{{ priceMask(cart) }} руб.</p> -->
    </div>
  </div>
  <div>Cart summ {{ cart }}</div>
</template>

<script setup>
const cart = useCart();
</script>

<style>

</style>
