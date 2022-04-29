<template>
  <div>
    <laser-list class="v-bodys" />
  </div>
</template>

<script>
//import UserInfo from './components/UserInfoHash.vue';
//import MenuTableFood from './components/MenuTableFood.vue';
import LaserList from "./makegood/LaserList.vue";

export default {
  name: "App",

  components: {
    //UserInfo,
    //MenuTableFood,
    LaserList,
  },

  data: () => ({
    //
  }),
};
</script>
<style scoped>
.v-bodys {
  background: linear-gradient(-45deg, #160623, #251343, #742152, #ca1e82);
  background-size: 400% 400%;
  animation: colorchange 10s ease infinite;
}
@keyframes colorchange {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
</style>