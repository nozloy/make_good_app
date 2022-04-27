<template>
<div class="standarttable" min-width="100%">
    <v-table>
    <thead>
      <tr>
        <th class="text-left">
          Холодные закуски
        </th>
        <th class="text-center" width="35%">
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
  <div>

        <div @click="item.dialog = true">
         {{ item.name }}<div v-show="item.quantity > 0" style="display: inline-block;">
            <v-chip
          color="success"
          density="compact"
        ><strong>{{item.quantity}}</strong>
        </v-chip>
            </div>
        </div>

    <v-dialog
      v-model="item.dialog"
      min-width="100%"
    >
      <v-card
      class="mx-auto"
      >
          <v-img
            class="align-end text-white"
            :src= "item.imageUrl"
            cover
    >
    <v-card-title>{{item.name}}</v-card-title>
    </v-img>
        <v-card-text>
          {{item.weight}} <br>
          {{item.description}}
        </v-card-text>
        <v-card-actions>
          <v-btn color="green" block @click="item.dialog = false">Закрыть</v-btn>
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
          size="small"
           ></v-btn>
            <v-btn
        variant="text"  
          @click="addItem(item)"  
          icon="mdi-plus-circle"
          color="success"
          size="small"
           ></v-btn>
          </td>
      </tr>
    </tbody>
  </v-table>
</div>
</template>

<script>
export default {
    setup() {

    },
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