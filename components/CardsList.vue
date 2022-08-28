<template>
  <div class="cards-list">
    <div class="card" v-for="card in cards" :key="card.char_id">
      <Card :card="card" />
    </div>
  </div>
</template>

<script setup>
  const { data: cards } = await useFetch(
    "https://www.breakingbadapi.com/api/characters/"
  );
  cards.value.forEach((e) => (e.count = 0));
  cards.value.forEach(
    (e) => (e.price = Math.floor(Math.random() * 60000) + 10000)
  );
  console.log(cards);
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
  margin: 0 0 30px 20px;
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