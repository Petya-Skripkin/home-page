<template>
  <div>
    <MyTip />
  </div> 
</template>

<script>
import MyTip from './components/MyTip.vue';
export default {
  name: "App",
  components: {
    MyTip
},
};
</script>

<style>
@import url(@/fonts/font.css);

body {
  font-family: "Manrope";
  background: #f7f7f7;
}
</style>
