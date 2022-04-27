<template>
  <v-app>
    <v-main>
      <Suspense>
      <template #default>
      <menu-table-food/>
      </template>
      <template #fallback>
      <v-progress-circular
      :size="70"
      :width="7"
      color="green"
      indeterminate
    ></v-progress-circular>
      </template>
      </Suspense>
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
