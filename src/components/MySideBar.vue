<template>
  <div class="sidebar">
    <a v-for="link in links" :key="link.key" :href="link.href" class="sidebar__link">
      <img :src="require(`@/assets/icons/${link.icon}`)" alt="" class="logo" />
      {{ link.title }}
    </a>
  </div>
</template>

<script>
export default {
  props: {
    links: Array,
  },
};
</script>

<style scoped>
.sidebar {
  flex: 1;
  padding: 18px 16px 16px 18px;
  background: #ffffff;
  border-radius: 8px;
  margin-right: 32px;
  padding-bottom: 100px;
}

.sidebar__link {
  display: flex;
  align-items: center;
  margin: 22px 0;
  font-family: "Manrope";
  font-style: normal;
  font-weight: 400;
  font-size: 13px;
  line-height: 17px;
  /* identical to box height, or 131% */

  color: #000000;
  text-decoration: none;
}

.logo {
  margin-right: 10px;
}
</style>