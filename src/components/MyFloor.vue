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
      <h2 class="title">{{ contacts.title }}</h2>
      <p class="text phone">{{ contacts.phone }}</p>
      <p class="text">{{ contacts.text }}</p>
      <a
        v-for="item in contacts.links"
        :key="item.text"
        :href="item.link"
        class="contacts__link text"
        >{{ item.text }}</a
      >
    </div>
  </div>
</template>

<script>
import MyLinks from "./MyLinks.vue";
export default {
  props: {
    linkTitle: String,
    userTitle: String,
    serviseTitle: String,
    radios: Array,
    networks: Array,
    links: Array,
    users: Array,
    servises: Array,
    contacts: Object,
  },
  data() {
    return {
      checked: "Номер телефона",
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
  color: #029aad;
}
</style>