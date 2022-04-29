<template>
  <v-card>
    <v-img
      @click="$emit('open')"
      :src="work.imageUrl"
      class="white--text align-end"
      gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
      height="200px"
      cover
    >
      <v-card-title class="text-white" v-text="work.name"></v-card-title>
    </v-img>
    <!-- <v-card-actions>
      <v-spacer></v-spacer>
      <v-btn
        size="small"
        color="surface-variant"
        variant="text"
        icon="mdi-heart"
      ></v-btn>
      <v-btn
        size="small"
        color="surface-variant"
        variant="text"
        icon="mdi-share-variant"
      ></v-btn>
    </v-card-actions> -->
  </v-card>
</template>

<script>
export default {
  props: {
    work: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style>
</style>