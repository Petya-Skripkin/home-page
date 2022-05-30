<template>
  <div class="slider">
    <div v-for="item in slide" :key="item.id" class="slide">
      <img
        :src="require(`@/assets/${item.img}`)"
        alt=""
        class="slide"
        v-if="item.id === count"
      />
    </div>
    <div class="slide__buttons">
      <button class="btn" @click="CounterMinus">
        <img src="@/assets/icons/Arrow.svg" alt="" style="height: 20px" />
      </button>
      <p class="number">1</p>
      <div class="slide__line">
        <div :class="`line ${slide.length/3 < count && 'line__active'}`">-</div>
        <div :class="`line ${slide.length/2 < count && 'line__active'}`">-</div>
        <div :class="`line ${slide.length/1 <= count && 'line__active'}`">-</div>
      </div>
      <p class="number">{{slide.length}}</p>
      <button class="btn" @click="CounterPlus">
        <img
          src="@/assets/icons/Arrow.svg"
          alt=""
          style="height: 20px; transform: matrix(-1, 0, 0, 1, 0, 0)"
        />
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    slide: Array,
  },
  data() {
    return {
      count: 1,
    };
  },
  methods: {
    CounterMinus() {
      if(this.count !== 1) this.count--
    },
    CounterPlus() {
      if(this.count !== this.slide.length) this.count++
    }
  }
};
</script>

<style scoped>
.slider {
  position: relative;
  flex: 4;
  border-radius: 8px;
}

.slide {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.slide__buttons {
  position: absolute;
  left: 50%;
  right: 50%;
  bottom: 23px;
  display: flex;
  align-items: center;
  color: white;
}

.btn {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px 15px;
  background: #ffffff;
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 50%;
  cursor: pointer;
}

.number {
  margin: 0 15px;
}

.slide__line {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 34px;
  height: 3px;
  border-radius: 2px;
  background: #fb791b;
}

.line {
  flex: 1;
  border-radius: 2px;
  color: #fb791b;
}

.line__active {
  color: white;
}
</style>