<template>
  <v-card class="mx-auto" max-width="1000">
    <v-container fluid>
      <v-row dense>
        <transition-group
          appear
          name="slidein"
          @before-enter="onBeforeEnter"
          @enter="onEnter"
          @leave="onLeave"
          :css="false"
        >
          <v-col
            v-for="(work, index) in works"
            :key="work.name"
            :data-index="index"
          >
            <div class="card">
              <work-card :work="work" @open="work.dialog = true" />
            </div>
            <v-dialog
              v-model="work.dialog"
              transition="dialog-bottom-transition"
            >
              <v-card class="mx-auto">
                <v-img
                  @click="work.dialog = false"
                  class="align-end"
                  :src="work.imageUrl"
                  cover
                >
                  <v-card-title class="justify-center">
                    <v-sheet
                      class="rounded-xl rounded-br-0 text-center"
                      color="purple darken-2"
                      style="padding-left: 10px; padding-right: 10px"
                      ><span class="text-white">{{ work.name }}</span></v-sheet
                    >
                  </v-card-title>
                </v-img>
                <v-card-subtitle class="pt-4">
                  {{ work.buyer }}
                </v-card-subtitle>
                <v-card-text @click="work.dialog = false">
                  <div style="white-space:pre-wrap;">{{ work.description }}</div>
                </v-card-text>
                <v-card-actions
                  class="justify-center"
                  style="margin-bottom: 15px"
                >
                  <v-btn
                    variant="outlined"
                    color="purple darken-2"
                    prepend-icon="mdi-send"
                    >Написать</v-btn
                  >
                </v-card-actions>
              </v-card>
            </v-dialog>
          </v-col>
        </transition-group>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
import WorkCard from "./WorkCard";
import gsap from "gsap";

export default {
  components: {
    WorkCard,
  },
  setup() {},
  props: {
    works: {
      type: Array,
      required: true,
    },
  },
  computed: {},
  data() {
    return {};
  },
  methods: {
    onBeforeEnter(el) {
      el.style.opacity = 0;
      el.style.height = "100%";
      el.style.transform = "translateX(200px)";
    },
    onEnter(el, done) {
      gsap.to(el, {
        opacity: 1,
        x: 0,
        delay: el.dataset.index * 0.1,
        onComplete: done,
      });
    },
    onLeave(el, done) {
      gsap.to(el, {
        opacity: 0,
        delay: el.dataset.index * 0.25,
        onComplete: done,
      });
    },
  },
};
</script>

<style scoped>
.dialog-bottom-transition-enter-active {
  transition: all 10s ease;
}
.dialog-bottom-transition-leave-active {
  transition: all 10s;
}
.dialog-bottom-transition-enter,
.dialog-bottom-transition-leave-to {
  opacity: 0;
}
.v-card-actions {
  padding: 0.25rem;
}
/* .slidein-enter-from {
  opacity: 0;
  transform: scale(0.1);
  transform: translateX(30px);
}
.slidein-leave-to {
  opacity: 0;
  transform: translateX(30px);
}
.slidein-enter-to {
  opacity: 1;
  transform: scale(1);
}
.slidein-enter-active {
  transition: all 0.5s ease;
  transition-delay: calc(0.5s * v-bind(index));
} */
</style>