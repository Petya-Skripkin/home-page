<template>
  <div class="product">
    <img :src="require(`@/assets/${img}`)" alt="" class="product__image" />
    <p class="product__desk">
      {{title}}
    </p>
    <div class="price__box">
      <h3 v-if="oldPrice" class="product__price promotion">{{oldPrice}}</h3>
      <h3 class="product__price">{{price}}</h3>
    </div>
    <button class="basket" @click="Basket">
      <img src="@/assets/icons/basket.svg" alt="" style="height: 15px" />
    </button>
    <div v-if="colors" class="radio">
      <label
        v-for="color in colors"
        :key="color.colorName"
        :class="`radio__label ${selectedColor === color.colorName && 'active'}`"
      >
        <p
          class="point"
          :style="
            color.color
              ? `background: ${color.color}`
              : `border:${color.border}; height: 12px;`
          "
        ></p>
        <input
          style="display: none"
          type="radio"
          :value="color.colorName"
          v-model="selectedColor"
        />
      </label>
    </div>
    <div v-if="bookmarks" class="bookmark">
      <div v-for="item in bookmarks" :key="item.id">
        <div class="bookmark__item" :style="`background: ${item.color}`">
          <img
            v-if="item.icon"
            :src="require(`@/assets/icons/${item.icon}`)"
            alt=""
            class="icon"
          />
          <p v-else class="item">{{ item.title }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "Планшет Samsung Galaxy Tab S8 11 128GB Silver (SM-X706)",
      img: "tablet.png",
      price: "499 890 ₸",
      oldPrice: "499 890 ₸",
      selectedColor: "red",
      colors: [
        {
          colorName: "red",
          color: "linear-gradient(180deg, #F857A6 0%, #FF5858 100%)",
        },
        {
          colorName: "white",
          border: "0.6px solid rgba(31, 31, 31, 0.12)",
        },
        {
          colorName: "black",
          color: "linear-gradient(180deg, #232526 0%, #414345 100%)",
        },
        {
          colorName: "green",
          color: "linear-gradient(180deg, #34E89E 0%, #0F3443 100%)",
        },
        {
          colorName: "orange",
          color: "linear-gradient(180deg, #FF4B1F 0%, #FF9068 100%)",
        },
      ],
      bookmarks: [
        {
          id: 0,
          color:
            "linear-gradient(91.87deg, #FF00B8 0.42%, #B009FE 37.09%, #3E1FFC 65.17%, #00DEFF 103.84%);",
          title: "Хит продаж",
        },
        {
          id: 3,
          color: "#FFCD00",
          title: "Новинка",
        },
        {
          id: 2,
          color: "#FF3B30",
          title: "-20%",
        },
        {
          id: 1,
          color: "#62D44D",
          icon: "gift.svg",
        },
      ],
    };
  },
};
</script>

<style scoped>
.product {
  position: relative;
  padding: 12px 22px;
  background: #ffffff;
  /* Evrika/background */

  border: 1px solid #f7f7f7;
  border-radius: 8px;
}

.product__image {
  height: 156.68px;
  margin-bottom: 45px;
}

.product__desk {
  font-family: "Manrope";
  font-style: normal;
  font-weight: 400;
  font-size: 13.6px;
  line-height: 18px;
  /* or 132% */

  display: flex;
  align-items: center;
  letter-spacing: 0.5px;

  color: #000000;
}

.price__box {
  display: flex;
  flex-direction: column;
  align-items: left;
}

.product__price {
  margin: 5px;
  font-family: "Manrope";
  font-style: normal;
  font-weight: 700;
  font-size: 19px;
  line-height: 18px;
  /* identical to box height, or 95% */

  display: flex;
  align-items: center;
  letter-spacing: 0.5px;

  color: #000000;
}

.promotion {
  font-weight: 700;
  font-size: 19px;
  line-height: 18px;
  /* identical to box height, or 95% */

  letter-spacing: 0.5px;
  text-decoration-line: line-through;

  color: #999999;
}

.basket {
  position: absolute;
  bottom: 20px;
  right: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 0px;
  width: 40px;
  height: 40px;
  border: none;
  border-radius: 50px;
  background: #00bccc;
  cursor: pointer;
  box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.25);
}

.radio {
  position: absolute;
  top: 50%;
  transform: translate(0, -50%);
  right: 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: auto;
}

.radio__label {
  display: inline-flex;
  align-items: center;
  width: 14px;
  height: 14px;
  border-radius: 50%;
  cursor: pointer;
  margin: 3px;
}

.point {
  display: inline-block;
  width: 14px;
  height: 14px;
  border-radius: 50%;
}

.active {
  padding: 4px;
  border: 1px solid #dee0e6;
}

.bookmark {
  position: absolute;
  top: 10%;
  left: -4px;
  transform: translate(0, -10%);
  display: flex;
  flex-direction: column;
  border-radius: 0px 3px 3px 8px;
}

.bookmark__item {
  display: inline-block;
  margin-bottom: 7px;
  border-radius: 0px 3px 3px 8px;
  color: white;
}

.item {
  padding: 10px;
  margin: 0;
  font-style: normal;
  font-weight: 800;
  font-size: 10px;
  line-height: 0;
}

.icon {
  height: 15px;
  padding: 0 10px;
  margin: 0;
}
</style>