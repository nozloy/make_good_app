<template>
<div class="standarttable">
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
          <td>
            {{ item.quantity }}
            <v-btn
        variant="text"  
          @click="removeItem(item)"  
          size="small"
          icon="mdi-minus-circle"
          color="error"
           ></v-btn>  
            <v-btn
        variant="text"  
          @click="addItem(item)"  
          size="small"
          icon="mdi-plus-circle"
          color="success"
           ></v-btn>
          </td>
      </tr>
    </tbody>
  </v-table>
</div> 
</template>

<script>
export default {
    props: {
        snacks: {
            type:Array,
            required: true,
        }
    },
    data() {
        return{
        }
    },
        methods:{
      addItem (item){
        if(item.quantity < 5){
        item.quantity +=1;
        }
      },
      removeItem (item){
        if(item.quantity > 0){
        item.quantity -=1;
        } else {
          item.quantity = 0;
        }
      }
    }
    

}
</script>

<style>

</style>