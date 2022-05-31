<template>
  <div class="roll mr">
    <h1 class="roll__title">EVRIKA | надежная электроника и бытовая техника</h1>
    <div class="roll__content">
      <div class="roll__visible">
        <p class="roll__text">
          EVRIKA является ведущей сетью на рынке потребительской электроники
          южного региона, осуществляющая свою деятельность с 2000 года. Сегодня
          сеть гипермаркетов электроники и бытовой техники EVRIKA включает 30
          магазинов, в 22 населенных пунктах Казахстана: Нур-Султан, Алматы,
          Шымкент, Аксукент, Аральск, Арысь, Жаркент, Жетысай, Карабулак,
          Караганда, Каскелен, Кызылорда, Ленгер, с.Казыгурт, с.Турара
          Рыскулова, с. Сарыкемер, с. Торетам, с. Узынагаш, Сарыагаш, Тараз,
          Туркестан, Шу.
        </p>
        <p class="roll__text">
          География присутствия компании постоянно расширяется. Благодаря
          качественным товарам от ведущих мировых брендов, конкурентной ценовой
          политике, высококлассному формату магазинов, соответствующих
          международным стандартам и клиенто-ориентированному сервису EVRIKA
          отвечает всем требованиям своих любимых клиентов.
        </p>
      </div>
      <div v-if="visible" class="roll__visible">
        <p class="roll__text">
          EVRIKA является ведущей сетью на рынке потребительской электроники
          южного региона, осуществляющая свою деятельность с 2000 года. Сегодня
          сеть гипермаркетов электроники и бытовой техники EVRIKA включает 30
          магазинов, в 22 населенных пунктах Казахстана: Нур-Султан, Алматы,
          Шымкент, Аксукент, Аральск, Арысь, Жаркент, Жетысай, Карабулак,
          Караганда, Каскелен, Кызылорда, Ленгер, с.Казыгурт, с.Турара
          Рыскулова, с. Сарыкемер, с. Торетам, с. Узынагаш, Сарыагаш, Тараз,
          Туркестан, Шу.
        </p>
        <p class="roll__text">
          География присутствия компании постоянно расширяется. Благодаря
          качественным товарам от ведущих мировых брендов, конкурентной ценовой
          политике, высококлассному формату магазинов, соответствующих
          международным стандартам и клиенто-ориентированному сервису EVRIKA
          отвечает всем требованиям своих любимых клиентов.
        </p>
      </div>
      <button class="roll__btn" @click="setVisible">
        ПОДРОБНЕЕ
        <img
          :style="`margin-left: 5px; ${
            visible && 'transform: rotate(180deg);'
          }`"
          src="@/assets/ArrowChevronDown.png"
          alt=""
        />
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      visible: false,
    };
  },
  methods: {
    setVisible() {
      this.visible = !this.visible;
    },
  },
};
</script>

<style>
.roll__title {
  margin-top: 30px;
  font-size: 28.5px;
  line-height: 20px;
  /* identical to box height, or 70% */

  display: flex;
  align-items: center;

  color: #000000;
}

.roll__content {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: #ffffff;
  border-radius: 8px;
  padding: 24px;
}

.roll__visible {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin: 0 -16px;
  margin-bottom: 16px;
}

.roll__text {
  flex: 1;
  margin: 0 16px;
  font-size: 14px;
  line-height: 16px;
  /* or 114% */

  /* Evrika/border-solid2 */

  color: #999999;
}

.roll__btn {
  display: inline-flex;
  align-items: center;
  border: none;
  outline: none;

  font-weight: 700;
  font-size: 10px;
  line-height: 0px;
  /* identical to box height, or 0% */
  background: inherit;
  color: #019aac;
  cursor: pointer;
}
</style>