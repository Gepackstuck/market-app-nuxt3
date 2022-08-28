<template>
  <div class="card-footer">
    <div>
      <button class="btn" @click="add()">+</button>
      <button class="btn" @click="del()">-</button>
      <b class="count">{{ card.count }}</b>
    </div>
    <b>{{ priceMask(card.price) }} руб.</b>
  </div>
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
    add: function () {
      this.cart = this.cart + this.props.card.price;
      this.props.card.count = this.props.card.count + 1;
    },
    del: function () {
      if (this.props.card.count > 0) {
      this.cart = this.cart - this.props.card.price;
      this.props.card.count = this.props.card.count - 1;
      }
    }
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

.count {
  margin-left: 5px;
}
</style>
