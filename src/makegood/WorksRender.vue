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
                @click="work.dialog = true"
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
              <v-btn size="small" color="surface-variant" variant="text" icon="mdi-share-variant"></v-btn>
            </v-card-actions>
          </v-card>

                    <v-dialog
                    v-model="work.dialog"
                    transition="scale-transition"
    >
                <v-card
                class="mx-auto">
                        <v-img @click="work.dialog = false"
                        class="align-end"
                        :src= "work.imageUrl"
                        cover>
                <v-card-title class="justify-center">
                    <v-sheet
                        class="rounded-xl rounded-br-0 text-center"
                        color="purple darken-2"
                        style="padding-left: 10px;padding-right: 10px;"
                    ><span class="text-white">{{work.name}}</span></v-sheet>
                    
                    </v-card-title>
                </v-img>
                    <v-card-subtitle class="pt-4">
                {{work.buyer}}
                </v-card-subtitle>
                    <v-card-text @click="work.dialog = false">
                    <div>{{work.description}}</div>
                    </v-card-text>
                    <v-card-actions
                    class="justify-center"
                    style="margin-bottom:15px">
                            <v-btn
                            variant="outlined"
                            color="purple darken-2"
                            prepend-icon="mdi-send"
                            >Написать</v-btn>
            
                    </v-card-actions>
                </v-card>

                    </v-dialog>

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




}
</script>

<style>
.scroll-y-transition,
.scroll-y-transition {
  transition: transform 1.9s ease-in-out;
}
</style>