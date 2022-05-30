<template>
  <div>
    <MyTip :calls="calls" />
    <MyHeader :logo="logo" :basket="basket" :menu="menu" :placeholder="placeholder" />
  </div>
</template>

<script>
import MyTip from "./components/MyTip.vue";
import MyHeader from "./components/MyHeader.vue";
export default {
  name: "App",
  components: {
    MyTip,
    MyHeader,
},
  data() {
    return {
      calls: ["87056982391", "87077985572"],
      logo: "logo.svg",
      basket: {
        icon: "basket.svg",
        link: "#",
        count: 7,
        title: "Корзина",
        text: "2 102 820₸"
      },
      menu: [
        {
          key: 1,
          icon: "user.svg",
          href: "#",
        },
        {
          key: 2,
          icon: "scales.svg",
          href: "#",
        },
        {
          key: 3,
          icon: "heard.svg",
          href: "#",
          count: 2,
        },
      ],
      placeholder: "Ищите среди 10 000 товаров...",
    };
  },
};
</script>

<style>
@import url(@/fonts/font.css);

body {
  margin: 0;
  font-family: "Manrope";
  background: #f7f7f7;
}
</style>
