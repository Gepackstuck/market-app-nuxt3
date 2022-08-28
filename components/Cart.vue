<template>
  <div class="footer">
    <p class="cart">{{ priceMask(cart) }} руб.</p>
    <img src="svg\Cart.svg" />
  </div>
</template>

<script setup>
const cart = useCart();
function priceMask(price) {
  return new Intl.NumberFormat("ru-RU").format(price);
}
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
  justify-content: flex-end;
  opacity: 0.9;
  align-items: center;
  width: 100%;
}

.cart {
  color: white;
  margin-right: 6px;
}

.nav-btn {
  border: none;
  cursor: pointer;
  background-color: transparent;
  color: aliceblue;
}

img {
  margin-right: 169px;
}
</style>
