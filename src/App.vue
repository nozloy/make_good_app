<template>
  <v-app>
    <v-main>
      <div class="fullscreen">
  <div class="text-center">
    <v-btn
      color="primary"
      @click="dialog = true"
    >
      Open Dialog
    </v-btn>

    <v-dialog
      v-model="dialog"
    >
      <v-card>
        <v-card-text>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
        </v-card-text>
        <v-card-actions>
          <v-btn color="primary" block @click="dialog = false">Close Dialog</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
  </div>
    </v-main>
  </v-app>
</template>

<script>
//import UserInfo from './components/UserInfoHash.vue';
//import MenuTableFood from './components/MenuTableFood.vue';

export default {
  name: 'App',

  components: {
    //UserInfo,
    //MenuTableFood,
  },

  data: () => ({
    dialog: false,
  }),
}
</script>
<style scoped>
.fullscreen {
  min-width: none;
}
</style>
