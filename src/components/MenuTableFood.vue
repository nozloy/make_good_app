<template>
 <standart-table :snacks="snacks"/>
</template>

<script>
import StandartTable from './StandartTable.vue';
  export default {
      components: {
    StandartTable,
  },
    data () {
      return {
        snacks: [
          {
            name: 'Сэндвич с курицей и картофель фри',
            weight: "500г",
            description:"Булочка, куриное филе, салат айсберг, огурец, сыр чеддер и сливочно-базиличный соус. Гарнир - картофель фри",
            imageUrl: "https://eda.yandex/images/3667559/c49afefa1ca7bdd794ff917128d39aab-450x300.jpeg",
            quantity: 0,
            dialog: false,
          },
          {
            name: 'Салат Цезарь с креветками',
            weight: "280г",
            description:"Салат с креветками, томатами черри, гренками, сыром пармезан и соусом Цезарь",
            imageUrl: "https://eda.yandex/images/3583740/36fb108fd4abb376a6d2392eeb30d6b6-450x300.jpeg",
            quantity: 0,
            dialog: false,
          },

        ],
      }
    },

  }
</script>

<style>

</style>