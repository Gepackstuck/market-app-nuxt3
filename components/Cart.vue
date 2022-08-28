<template>
    <div class="footer">
      <p class="nav">navigation</p>
      <p class="cart">{{ priceMask(cart) }} руб.</p>
    </div>
</template>

<script setup>
const cart = useCart();
function priceMask(price) {
      return new Intl.NumberFormat("ru-RU").format(price);
    };
</script>

<style>
  .footer {
    background-color: black;
    position: sticky;
    bottom: 0;
    height: 60px;
    padding: 0;
    display: flex;
    margin: auto;
    justify-content: space-between;
    opacity: 0.9;
  }
  
  .nav {
    color: white;
    margin-left: 50%;
  }
  
  .cart {
    color: white;
    margin-right: 30px;
  }
  </style>
