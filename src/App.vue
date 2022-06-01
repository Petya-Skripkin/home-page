<template>
  <div>
    <MyTip :calls="calls" />
    <MyHeader
      :logo="logo"
      :basket="basket"
      :menu="menu"
      :placeholder="placeholder"
    />
    <div class="mr flex__conteiner">
      <MySideBar :links="links" />
      <MySlider :slide="slide" />
    </div>
    <div class="products mr">
      <h1 class="news">Новинки</h1>
      <div class="product__conteiner">
        <div v-for="product in products" :key="product.id" class="product__box">
          <MyProduct
            :bookmarks="product.bookmarks"
            :colors="product.colors"
            :img="product.img"
            :oldPrice="product.oldPrice"
            :price="product.price"
            :title="product.title"
            @basket="Basket"
          />
        </div>
      </div>
    </div>
    <div class="cards mr">
      <MyCard :cards="cards" />
    </div>
    <MyRoll :title="roll.title" :texts="roll.texts" />
    <MyFloor
      :contacts="floor.contacts"
      :links="floor.links"
      :linkTitle="floor.linkTitle"
      :networks="floor.networks"
      :radios="floor.radios"
      :servises="floor.servises"
      :serviseTitle="floor.serviseTitle"
      :users="floor.users"
      :userTitle="floor.userTitle"
    />
    <div class="footer">
      <img
        :src="require(`@/assets/icons/${logo}`)"
        alt=""
        class="footer__icon"
      />
      <a :href="footer.link.href" class="footer__link"
        >
        {{footer.link.title}}
      </a>
      <p class="footer__company">
        {{footer.text}}
      </p>
    </div>
  </div>
</template>

<script>
import MyTip from "@/components/MyTip.vue";
import MyHeader from "@/components/MyHeader.vue";
import MySideBar from "@/components/MySideBar.vue";
import MySlider from "@/components/MySlider.vue";
import MyProduct from "@/components/MyProduct.vue";
import MyCard from "@/components/MyCard.vue";
import MyRoll from "@/components/MyRoll.vue";
import MyFloor from "@/components/MyFloor.vue";
import * as mock from "@/mock";

export default {
  name: "App",
  components: {
    MyTip,
    MyHeader,
    MySideBar,
    MySlider,
    MyProduct,
    MyCard,
    MyRoll,
    MyFloor,
  },
  data() {
    return {
      logo: mock.logo,
      placeholder: mock.placeholder,
      calls: mock.calls,
      basket: mock.basket,
      menu: mock.menu,
      links: mock.links,
      slide: mock.slide,
      products: mock.products,
      cards: mock.cards,
      roll: mock.roll,
      floor: mock.floor,
      footer: mock.footer,
    };
  },
  methods: {
    Basket(e) {
      console.log(e);
    },
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

.mr {
  margin: 0 48px;
}

.flex__conteiner {
  display: flex;
  margin-top: 24px;
}

.news {
  margin-top: 32px;
  font-weight: 800;
  font-size: 28.5px;
  line-height: 18px;
  /* identical to box height, or 63% */

  color: #000000;
}

.product__conteiner {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}

.product__box {
  width: 242px;
  margin-bottom: 8px;
}

.cards {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 32px;
}

.footer {
  display: flex;
  align-items: center;
  padding: 36px 48px;
  background: #141a38;
}

.footer__icon {
  height: 18px;
}

.footer__link {
  margin: auto;
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 10px;
  line-height: 17px;
  /* identical to box height, or 170% */

  letter-spacing: 0.05em;

  color: #ffffff;
  text-decoration: none;
  text-align: center;
}

.footer__company {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 10px;
  line-height: 17px;
  /* identical to box height, or 170% */

  letter-spacing: 0.05em;

  text-align: center;
  color: #ffffff;
}
</style>
