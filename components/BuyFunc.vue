<template>
  <div class="card-footer"></div>
  <div>
    <button @click="cart += +value, card.count += 1">+</button>
    <button @click="cart -= +value, card.count -= 1">-</button>
    <button @click="cart -= +value, card.count -= 1">0</button>
    <b>{{ card.count }}</b>
  </div>
  <p>{{ priceMask(card.price) }} руб.</p>
</template>

<script>
export default {
  props: ["value", "card"],
  setup(props) {
    const cart = useCart();
    return {
      cart,
      props,
    };
  },
  methods: {
    priceMask: function (price) {
      return new Intl.NumberFormat("ru-RU").format(price);
    },
  },
};
</script>

<style>
.card-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.btn {
  border: none;
  cursor: pointer;
  background-color: transparent;
}
</style>
