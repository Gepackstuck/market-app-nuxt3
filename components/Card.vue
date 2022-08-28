<template>
  <div class="head-card">
    <img class="user-avatar" :src="card.user.profile_image.small" />
    <div>
      <a :href="card.user.links.html" target="_blank" class="user-name">
        {{ card.user.name }}
      </a>
      <p class="user-nickname">@{{ card.user.instagram_username }}</p>
    </div>
  </div>
  <img class="user-img" :src="card.urls.regular" />
  <BuyFunc :value="card.price" :card="card" />
</template>

<script>
import BuyFunc from "./BuyFunc.vue";
export default {
  props: {
    card: Object,
  },
  setup(props) {
    const cart = useCart();
    return {
      props,
      cart,
    };
  },
  components: { BuyFunc },
};
</script>

<style>
.head-card {
  display: flex;
  align-items: center;
}

.user-avatar {
  width: 30px;
  height: 30px;
  margin-right: 10px;
  border-radius: 20px;
}

.user-name {
  text-decoration: none;
  width: 120px;
  height: 12px;
  font-style: normal;
  font-weight: 700;
  font-size: 12px;
  line-height: 14px;
  color: #333;
  cursor: pointer;
}

.user-nickname {
  width: 120px;
  height: 12px;
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  line-height: 14px;
  color: #8d8d8d;
  margin-top: 5px;
}

.user-img {
  width: 320px;
  height: 230px;
}
</style>
