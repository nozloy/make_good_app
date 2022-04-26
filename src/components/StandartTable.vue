<template>
<div class="standarttable">
    <v-table>
    <thead>
      <tr>
        <th class="text-left">
          Холодные закуски
        </th>
        <th class="text-center">
          Количество
        </th>
      </tr>
    </thead>
    <tbody>
      <tr
        v-for="item in snacks"
        :key="item.name"
      >
        <td>
  <div class="text-center">

    <v-dialog
      v-model="dialog"
    >
    <template v-slot:activator="{ props }">
        <div
          v-bind="props"
        >
         {{ item.name }}<div v-show="item.quantity > 0" style="display: inline-block;">
            <v-chip
          color="success"
          density="compact"
        ><strong>{{item.quantity}}</strong>
        </v-chip>
            </div>
        </div>
      </template>


      <v-card>
        <v-card-text>
          {{item.weight}}
        </v-card-text>
        <v-card-actions>
          <v-btn color="green" block @click="dialog = false">Закрыть</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
            
        </td>
          <td class="text-center">  
            <v-btn
        variant="text"  
          @click="removeItem(item)"  
          icon="mdi-minus-circle"
          color="error"
          size="x-large"
           ></v-btn>
            <v-btn
        variant="text"  
          @click="addItem(item)"  
          icon="mdi-plus-circle"
          color="success"
          size="x-large"
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
      },
    //   expand(item){

    //   }
    }
    

}
</script>

<style>

</style>