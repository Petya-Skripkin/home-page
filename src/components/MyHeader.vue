<template>
  <div class="header">
    <img :src="require(`@/assets/icons/${logo}`)" alt="" class="logo" />
    <input type="text" class="search" :placeholder="placeholder" />
    <ul class="menu">
      <li class="menu__item" v-for="item in menu" :key="item.key">
        <a :href="item.href" class="item__link">
          <img
            :src="require(`@/assets/icons/${item.icon}`)"
            alt=""
            class="item__icon"
          />
          <div v-if="item.count" class="count">{{ item.count }}</div>
        </a>
      </li>
      <a :href="basket.link" class="item__link">
        <li class="menu__item">
          <img
            :src="require(`@/assets/icons/${basket.icon}`)"
            alt=""
            class="item__icon"
          />
          <div v-if="basket.count" class="count">{{ basket.count }}</div>
        </li>
        <div class="basket">
          <h4 style="font-size: 16px; margin: 0; margin-bottom: 10px;">{{basket.title}}</h4>
          {{basket.text}}  
        </div>
      </a>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    logo: String,
    basket: {
      icon: String,
      link: String,
      count: Number,
      title: String,
      text: String,
    },
    menu: Array,
    placeholder: String,
  },
};
</script>

<style>
.header {
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 13px;
  margin: 0;
  margin-top: 10px;
  border: 0;
  background: #029aad;
}
.search {
  min-width: 50%;
  background: #ffffff;
  /* Neutrals/White */
  padding: 13px 16px;

  border: 1px solid #ffffff;
  border-radius: 8px;

  font-family: "Manrope";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 22px;

  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  outline: 0;
  background-image: url("@/assets/SearchIcon.png");
  background-repeat: no-repeat;
  background-position: 98% 55%;
  cursor: pointer;
}

.menu {
  display: flex;
  align-items: center;
}

.menu__item {
  display: inline-block;
  position: relative;
  margin: 0 15px;
}

.item__icon {
  height: 25px;
}

.item__link {
  display: flex;
  align-items: center;
  color: white;
  text-decoration: none;
  line-height: 5px;
  font-size: 11px;
}

.count {
  position: absolute;
  top: -10px;
  right: -10px;
  padding: 5px 8px;
  border-radius: 30px;
  background: #fb791b;
  color: white;
  font-family: "Manrope";
  font-style: normal;
  font-weight: 800;
  font-size: 11px;
  line-height: 10px;
}
</style>