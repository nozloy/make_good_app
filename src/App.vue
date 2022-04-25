<template>
  <v-app>
    <v-main>
      <user-info/>
    </v-main>
  </v-app>
</template>

<script>
import UserInfo from './components/UserInfo.vue';

export default {
  name: 'App',

  components: {
    UserInfo,
  },

  data: () => ({
    //
  }),
}
</script>
