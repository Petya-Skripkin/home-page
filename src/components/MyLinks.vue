<template>
  <div class="links">
    <h2 class="title">{{title}}</h2>
    <a
      v-for="link in links"
      :key="link.title"
      :href="link.link"
      class="links__link text"
      >{{ link.title }}</a
    >
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    links: Array,
  },
};
</script>

<style>
.text {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  line-height: 17px;
  /* or 142% */

  letter-spacing: 0.02em;

  /* Evrika/border-solid2 */

  color: #999999;
}

.title {
  font-weight: 800;
  font-size: 16px;
  line-height: 16px;
  color: #000000;
}

.links {
  flex: 1;
  display: flex;
  flex-direction: column;
}

.links__link {
  text-decoration: none;
  margin-bottom: 8px;
}
</style>