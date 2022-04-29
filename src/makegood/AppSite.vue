<template>
        <div>
         <v-card
    class="mx-auto"
    max-width="448"
  >
    <v-layout>
      <transition name="v-app-bar-enter-active">
      <v-app-bar
        density="compact">
        <template v-slot:prepend>
          <v-app-bar-nav-icon class="text-white"></v-app-bar-nav-icon>
        </template>
        <div class="justify-center">
        <v-app-bar-title class="text-white"><h3>Laser [MakeGood]</h3></v-app-bar-title>
        </div>
        <template v-slot:append>
          <v-btn class="text-white" icon="mdi-dots-vertical"></v-btn>
        </template>
      </v-app-bar>
      </transition>
      <v-main>
       <laser-list/> 
      </v-main>
    </v-layout>
  </v-card>
        </div>
</template>

<script>
//import UserInfo from './components/UserInfoHash.vue';
//import MenuTableFood from './components/MenuTableFood.vue';
import LaserList from './makegood/LaserList.vue';

export default {
  name: 'App',

  components: {
    //UserInfo,
    //MenuTableFood,
    LaserList,
  },

  data: () => ({
    //
  }),

}
</script>
<style scoped>
/* .v-app-bar {
  
} */
.v-app-bar {
  background: linear-gradient(-45deg, #160623, #251343, #030104, #ca1e82);
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