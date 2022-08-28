<template>
  <div class="cards-list">
    <div class="card" v-for="card in cards" :key="card.char_id">
      <Card :card="card" />
    </div>
    <div class="nav">
      <button class="nav-btn">← Предыдущая</button>
      <button class="nav-btn">Следующая →</button>
    </div>
  </div>
</template>

<script setup>
const clientID = "WJx3zk71hArFTdGw_Ie4odVp-LDPziLYRnCfipbv3TU";
const { data: cards } = await useFetch(
  `https://api.unsplash.com/photos?client_id=${clientID}`
);
cards.value.forEach((e) => (e.count = 0));
cards.value.forEach(
  (e) => (e.price = Math.floor(Math.random() * 60000) + 10000)
);
console.log(cards.value);
</script>

<style>
.cards-list {
  background: #fff;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  padding: 20px 0;
  margin: 0 auto;
}

.card {
  width: 320px;
  height: 312px;
  background: #fffefb;
  border-radius: 4px;
  margin: 0 0 10px 20px;
}

.nav {
  color: white;
  position: sticky;
  bottom: 0;
  height: 60px;
  width: 100%;
  display: flex;
  justify-content: center;
  z-index: 99;
}

@media (min-width: 1000px) {
  .cards-list {
    width: 980px;
  }
}

@media (min-width: 768px) and (max-width: 999px) {
  .cards-list {
    width: 768px;
  }
}

@media (min-width: 480px) and (max-width: 767px) {
  .cards-list {
    width: 480px;
  }
}

@media (min-width: 320px) and (max-width: 479px) {
  .cards-list {
    width: 320px;
  }
}
</style>
