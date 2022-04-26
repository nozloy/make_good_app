<template>
<div class="standarttable">
    <v-table>
    <thead>
      <tr>
        <th class="text-left">
          Холодные закуски
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
          <td>
            
            <v-btn
        variant="text"  
          @click="removeItem(item)"  
          icon="mdi-minus-circle"
          color="error"
          size="large"
           ></v-btn> 
           {{ item.quantity }} 
            <v-btn
        variant="text"  
          @click="addItem(item)"  
          icon="mdi-plus-circle"
          color="success"
          size="large"
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