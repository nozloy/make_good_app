<template>
<v-card
    class="mx-auto"
    max-width="400"
  >
    <v-img
      class="align-end text-white"
      height="200"
      src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
      cover
    >
      <v-card-title>Информация о пользователе</v-card-title>
    </v-img>

    <v-card-subtitle class="pt-4">
      {{userFirstName}} {{userLastName}} {{username}}
    </v-card-subtitle>

    <v-card-text>
      <div>Активная теама: {{theme}}</div>

      <div>Query ID: {{queryId}}</div>
    </v-card-text>

    <v-card-actions>
      <v-btn color="orange">
        Подробнее
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
    setup()
    {
        let theme = window.Telegram.WebApp.colorScheme;
        const initData = window.Telegram.WebApp.initData;
        const infoArray = initData.split("&");
        const userData = JSON.parse((decodeURIComponent(infoArray[1])).slice(5));
        const userFirstName = userData.first_name;
        const userLastName = userData.last_name;
        const id = userData.id;
        const username = userData.username;
        const queryId = (infoArray[0]).slice(9);
        const authDate = (infoArray[2]).slice(10);
        const hash = (infoArray[3]).slice(5);
        return {userFirstName, userLastName, id, username, queryId, authDate , hash, theme}
    }
}
</script>

<style>

</style>