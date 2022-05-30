<template>
  <div class="tip">
    <button class="location">
      <img class="img" src="@/assets/location.png" />
      Алматы
    </button>
    <!-- <select v-model.trim="nowCalled" class="select" @click="selectClick">
      <img src="@/assets/phone.png" alt="" class="phone">
      <option class="call" value="Помощь и консультация" disabled>
        Помощь и консультация
      </option>
      <option v-for="call of calls" :key="call" :value="call">
        {{ call }}
      </option>
    </select> -->
    <div class="select" @click="OnShow">
      <img src="@/assets/phone.png" alt="" class="phone" />
      {{ nowCalled }}
      <div v-if="show" class="select__conteiner">
        <label
          class="label"
          v-for="call in calls"
          :key="call"
          :for="call"
          @click.stop
        >
          <input
            class="radio"
            type="radio"
            name="number"
            :id="call"
            :value="call"
            v-model="nowCalled"
          />
          {{ call }}
        </label>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      nowCalled: "Помощь и консультация",
    };
  },
  props: {
    calls: {
      type: Array,
    },
  },
  methods: {
    OnShow() {
      this.show = !this.show;
    },
  },
  watch: {
    nowCalled() {
      this.show = !this.show;
    },
  },
};
</script>

<style scoped>
.tip {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.location {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 7.5px 13px;

  background: #ffffff;
  /* Evrika/gray */

  border: 1px solid #e0e0e0;
  border-radius: 30px;
  cursor: pointer;
}

.select {
  display: flex;
  position: relative;
  min-width: 200px;
  padding: 8px;
  padding-right: 30px;
  padding-left: 40px;
  background: #ffffff;
  /* Evrika/gray */

  border: 1px solid #e0e0e0;
  border-radius: 30px;

  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  outline: 0;
  background-image: url("@/assets/ArrowChevronDown.png");
  background-repeat: no-repeat;
  background-position: 95% 55%;
  cursor: pointer;
}

.select__conteiner {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 30px;
  left: 0;
  width: 100%;

  background: #ffffff;
  /* Evrika/gray */

  border: 1px solid #e0e0e0;
  border-radius: 2px 2px 10px 10px;
  cursor: pointer;
}

.radio {
  display: none;
}

.label {
  padding: 5px 15px;
  text-align: center;
  cursor: pointer;

  border-radius: 2px 2px 10px 10px;
}

.label:hover {
  background: #e0e0e0;
}

.phone {
  height: 24px;
  position: absolute;
  left: 13px;
  top: 0;
  bottom: 0;
  margin: auto;
}
</style>