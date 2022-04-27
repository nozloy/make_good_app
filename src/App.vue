<template>
  <v-app>
    <v-main>
      <menu-table-food/>
    </v-main>
  </v-app>
</template>

<script>
//import UserInfo from './components/UserInfoHash.vue';
import MenuTableFood from './components/MenuTableFood.vue';

export default {
  name: 'App',

  components: {
    //UserInfo,
    MenuTableFood,
  },

  data: () => ({
    //
  }),

}
</script>
