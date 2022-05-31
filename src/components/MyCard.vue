<template>
  <a v-for="item in cards" :key="item.id" :href="item.link" class="card">
    <img :src="require(`@/assets/icons/${item.logo}`)" alt="" class="card__image" />
  </a>
</template>

<script>
export default {
  props: {
    cards: Array,
  }
};
</script>

<style>
.card {
  display: inline-flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 12px;

  background: #ffffff;
  /* Shadow */

  box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.1),
    0px 1px 2px -1px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
}

.card__image {
  height: 22px;
}
</style>