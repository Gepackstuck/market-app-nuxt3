<template>
    <!-- <p class="user-avatar">{{ card.char_id }}</p> -->
    <p class="user-name">{{ card.name }}</p>
    <p class="user-nickname">@{{ card.nickname }}</p>
    <img class="user-img" :src="card.img" />
    <!-- <img src={card.user.profile_image.small}/>
        <p>{{card.user.first_name}}</p>
        <p>{{card.instagram_username}}</p>
        <p>@{{card.nickname}}</p>
        <img src={card.img}/> -->
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
.user-avatar {
  width: 30px;
  height: 30px;
}

.user-name {
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
}

.user-img {
  width: 320px;
  height: 230px;
}
</style>
