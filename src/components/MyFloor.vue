<template>
  <div class="floor">
    <div class="subskribe">
      <h2 class="title">Подписаться на нас</h2>
      <div class="subskribe__networks">
        <a
          v-for="item in networks"
          :key="item.img"
          :href="item.link"
          class="subskribe__icon"
        >
          <img :src="require(`@/assets/icons/${item.img}`)" alt="" />
        </a>
      </div>
      <p class="text">Получайте новые акции и скидки одним из первых</p>
      <div class="radio">
        <label v-for="radio in radios" :key="radio" class="radio__item">
          <span :class="`check ${checked === radio && 'active'}`"></span>
          <input
            type="radio"
            name="radio"
            :value="radio"
            v-model="checked"
            style="display: none"
          />
          {{ radio }}
        </label>
      </div>
      <input type="text" class="datas" :placeholder="checked" />
    </div>
    <MyLinks :title="linkTitle" :links="links" />
    <MyLinks :title="userTitle" :links="users" />
    <MyLinks :title="serviseTitle" :links="servises" />
    <div class="contacts">
      <h2 class="title">Контакты</h2>
      <p class="text phone">+7(771) 936-54-54</p>
      <p class="text">С 09:00 до 21:00 (без выходных)</p>
      <a href="#" class="contacts__link text">Написать на WhatsApp</a>
      <a href="#" class="contacts__link text">support@evrika.com</a>
    </div>
  </div>
</template>

<script>
import MyLinks from "./MyLinks.vue";
export default {
  data() {
    return {
      linkTitle: "Компания Evrika",
      userTitle: "Покупателям",
      serviseTitle: "Услуги и сервисы",
      checked: "Номер телефона",
      radios: ["Номер телефона", "Email"],
      networks: [
        {
          link: "#",
          img: "facebook.svg",
        },
        {
          link: "#",
          img: "odnoklassniki.svg",
        },
        {
          link: "#",
          img: "twitter.svg",
        },
        {
          link: "#",
          img: "vkontakte.svg",
        },
        {
          link: "#",
          img: "whatsapp.svg",
        },
      ],
      links: [
        {
          link: "#",
          title: "О компании",
        },
        {
          link: "#",
          title: "Магазины и пункты выдачи заказов",
        },
        {
          link: "#",
          title: "Корпоративные продажи",
        },
        {
          link: "#",
          title: "Новости",
        },
        {
          link: "#",
          title: "Вакансии",
        },
        {
          link: "#",
          title: "Авторизованные сервисные центры",
        },
        {
          link: "#",
          title: "Аренда торговых помещений",
        },
        {
          link: "#",
          title: "Контакты",
        },
      ],
      users: [
        {
          link: "#",
          title: "Акции",
        },
        {
          link: "#",
          title: "Каталог товаров",
        },
        {
          link: "#",
          title: "Доставка и оплата",
        },
        {
          link: "#",
          title: "Кредит и рассрочка",
        },
        {
          link: "#",
          title: "Возврат и обмен",
        },
        {
          link: "#",
          title: "Гарантия лучшей цены",
        },
        {
          link: "#",
          title: "Публичная оферта",
        },
        {
          link: "#",
          title: "FAQ",
        },
        {
          link: "#",
          title: "Вопросы по работе техники",
        },
      ],
      servises: [
        {
          link: "#",
          title: "Smart Service",
        },
        {
          link: "#",
          title: "Smart Bonus",
        },
        {
          link: "#",
          title: "Smart market",
        },
        {
          link: "#",
          title: "Smart Gift",
        },
        {
          link: "#",
          title: "Установка техники",
        },
      ],
    };
  },
  components: { MyLinks },
};
</script>

<style scoped>
.floor {
  display: flex;
  padding: 24px 48px;
  margin-top: 32px;
  background: #ffffff;
}

.subskribe {
  flex: 1;
  display: inline-flex;
  flex-direction: column;
  margin-right: 50px;
}

.title {
  font-weight: 800;
  font-size: 16px;
  line-height: 16px;
  color: #000000;
}

.subskribe__icon {
  margin-right: 16px;
}

.text {
  margin: 0;
  margin-bottom: 8px;
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

.radio {
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.radio__item {
  display: flex;
  align-items: center;
  font-family: "Manrope";
  font-style: normal;
  font-weight: 700;
  font-size: 15px;
  line-height: 16px;
  color: #000000;
  cursor: pointer;
}

.check {
  display: inline-block;
  width: 15px;
  height: 15px;
  margin-right: 10px;

  /* Neutrals/White */

  background: #ffffff;
  /* Evrika/background */

  border: 2px solid #f7f7f7;
  border-radius: 50%;
}

.active {
  border: 5px solid #fb791b;
}

.datas {
  margin-top: 22px;
  padding: 13px;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  font-family: "Manrope";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 22px;
  /* identical to box height, or 160% */

  /* Evrika/border-solid2 */

  color: #000;
  outline: none;
}

.contacts {
  flex: 1;
  display: flex;
  flex-direction: column;
}

.phone {
  font-size: 16px;
  color: #000000;
}

.contacts__link {
  text-decoration: none;
  color: #029AAD;
}
</style>