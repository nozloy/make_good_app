<template>
<div @submit.prevent="submit">
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
        <td @click="item.dialog = true">
  <div>
         {{ item.name }}<div v-show="item.quantity > 0" style="display: inline-block;">
            <v-chip
          color="success"
          density="compact"
        ><strong>{{item.quantity}}</strong>
        </v-chip>
            </div>

    <v-dialog
      v-model="item.dialog"
      transition="scroll-x-reverse-transition"
    >

      <v-card @click="item.dialog = false"
      class="mx-auto"
      >
      <Suspense>
        <template #default>
                    <v-img
            class="align-end"
            :src= "item.imageUrl"
            cover
    >
    <v-card-title class="justify-center">
        <v-sheet
            class="rounded-xl rounded-br-0 text-center"
            color="green darken-4"
            style="padding-left: 10px;padding-right: 10px;"
          ><span class="text-white">{{item.name}}</span></v-sheet>
        
        </v-card-title>
    </v-img>
        </template>
        <template #fallback>
<h4>Загрузка...</h4>
        </template>
      </Suspense>
        <v-card-subtitle class="pt-4">
      {{item.weight}}
    </v-card-subtitle>
        <v-card-text>
         <div>{{item.description}}</div>
        </v-card-text>
        <v-card-actions>
          
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
.scroll-x-reverse-transition-enter-active,
.scroll-x-reverse-transition-active {
  transition: transform .2s ease-in-out;
}
</style>