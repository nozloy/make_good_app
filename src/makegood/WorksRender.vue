<template>
 <v-card
    class="mx-auto"
    max-width="500"
  >
  <v-container fluid>
      <v-row dense>
        <v-col
          v-for="work in works"
          :key="work.name"
        >
          <v-card>
            <v-img
              :src="work.imageUrl"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="200px"
              cover
            >
              <v-card-title class="text-white" v-text="work.name"></v-card-title>
            </v-img>

            <v-card-actions>
              <v-spacer></v-spacer>

              <v-btn size="small" color="surface-variant" variant="text" icon="mdi-heart"></v-btn>

              <v-btn size="small" color="surface-variant" variant="text" icon="mdi-bookmark"></v-btn>

              <v-btn size="small" color="surface-variant" variant="text" icon="mdi-share-variant"></v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
  
</template>

<script>
export default {
    setup() {

    },
    props: {
        works: {
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

    }
}
</script>

<style>

</style>