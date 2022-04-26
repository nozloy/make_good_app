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
            name: 'Салат Каприз',
            weight: 159,
            quantity: 0,
          },
          {
            name: 'Салат Тещин язык',
            weight: 237,
            quantity: 0,
          },
          {
            name: 'Мясное удовольствие',
            weight: 262,
            quantity: 0,
          },
          {
            name: 'Салат из печени',
            weight: 305,
            quantity: 0,
          },
          {
            name: 'Салат «Фантазия»',
            weight: 356,
            quantity: 0,
          },
          {
            name: 'Салат «Мясной»',
            weight: 375,
            quantity: 0,
          },
          {
            name: 'Салат Оливье',
            weight: 392,
            quantity: 0,
          },
          {
            name: 'Салат «Пикантный»',
            weight: 408,
            quantity: 0,
          },
          {
            name: 'Салат «Будапешт»',
            weight: 452,
            quantity: 0,
          },
          {
            name: 'Салат "Ассоль"',
            weight: 518,
            quantity: 0,
          },
        ],
      }
    },

  }
</script>

<style>

</style>