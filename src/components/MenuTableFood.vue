<template>
   <v-table>
    <thead>
      <tr>
        <th class="text-left">
          Холодные закуски
        </th>
        <th class="text-left">
          Порция
        </th>
        <th class="text-left">
          Количество
        </th>
      </tr>
    </thead>
    <tbody>
      <tr
        v-for="item in snacks"
        :key="item.name"
      >
        <td>{{ item.name }}</td>
        <td>{{ item.weight }}</td>
          <td><v-btn @click="removeItem(item)"
          size="x-small"
          icon="mdi-chevron-left-circle"
          color="success"
           ></v-btn>
        {{item.quantity}}
            <v-btn @click="addItem(item)"
          size="x-small"
          icon="mdi-chevron-right-circle"
          color="success"
            ></v-btn>
          </td>
      </tr>
    </tbody>
  </v-table> 
</template>

<script>
  export default {
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
    methods:{
      addItem (item){
        item.quantity += 1;
        console.log(item.quantity);
      },
      removeItem (item){
        if(item.quantity > 0){
        item.quantity -=1;
        } else {
          item.quantity = 0;
        }
        
        console.log(item.quantity)
      }
    }
  }
</script>

<style>

</style>