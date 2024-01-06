<script lang="ts">
import { Toaster } from "vue-sonner";
import { authStore } from "@/store/auth";
import { ref, onMounted } from "vue";

export default {
  data: () => ({
    messages: [
      {
        time: "10:42am",
        color: "deep-purple-lighten-1",
      },
    ],
  }),
};
</script>

<template>
  <v-container>
    <v-row justify="space-around">
      <v-card class="mb-12" width="200">
        <v-img
          height="200"
          src="https://cdn.vuetifyjs.com/docs/images/cards/purple-flowers.jpg"
          cover
          class="text-white"
        >
          <!-- <v-toolbar color="rgba(0, 0, 0, 0)" theme="dark">
            <template v-slot:prepend>
              <v-btn icon="$menu"></v-btn>
            </template>

            <v-toolbar-title class="text-h6"> Messages </v-toolbar-title>

            <template v-slot:append>
              <v-btn icon="mdi-dots-vertical"></v-btn>
            </template>
          </v-toolbar> -->
        </v-img>

        <v-card-text>
          <div class="font-weight-bold ms-1 mb-2">Today</div>

          <v-timeline density="compact" align="start">
            <v-timeline-item
              v-for="message in messages"
              :key="message.time"
              :dot-color="message.color"
              size="sm"
            >
              <div class="mb-4">
                <div class="font-weight-normal">
                  <strong>{{ message.time }} </strong>
                </div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-card>

      <v-card class="mb-12" width="200">
        <v-img
          height="200"
          src="https://cdn.vuetifyjs.com/docs/images/cards/purple-flowers.jpg"
          cover
          class="text-white"
        >
          <!-- <v-toolbar color="rgba(0, 0, 0, 0)" theme="dark">
            <template v-slot:prepend>
              <v-btn icon="$menu"></v-btn>
            </template>

            <v-toolbar-title class="text-h6"> Messages </v-toolbar-title>

            <template v-slot:append>
              <v-btn icon="mdi-dots-vertical"></v-btn>
            </template>
          </v-toolbar> -->
        </v-img>

        <v-card-text>
          <div class="font-weight-bold ms-1 mb-2">Today</div>

          <v-timeline density="compact" align="start">
            <v-timeline-item
              v-for="message in messages"
              :key="message.time"
              :dot-color="message.color"
              size="sm"
            >
              <div class="mb-4">
                <div class="font-weight-normal">
                  <strong>{{ message.time }} </strong>
                </div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-card>

      <v-card class="mb-12" width="200">
        <v-img
          height="200"
          src="https://cdn.vuetifyjs.com/docs/images/cards/purple-flowers.jpg"
          cover
          class="text-white"
        >
          <!-- <v-toolbar color="rgba(0, 0, 0, 0)" theme="dark">
            <template v-slot:prepend>
              <v-btn icon="$menu"></v-btn>
            </template>

            <v-toolbar-title class="text-h6"> Messages </v-toolbar-title>

            <template v-slot:append>
              <v-btn icon="mdi-dots-vertical"></v-btn>
            </template>
          </v-toolbar> -->
        </v-img>

        <v-card-text>
          <div class="font-weight-bold ms-1 mb-2">Today</div>

          <v-timeline density="compact" align="start">
            <v-timeline-item
              v-for="message in messages"
              :key="message.time"
              :dot-color="message.color"
              size="sm"
            >
              <div class="mb-4">
                <div class="font-weight-normal">
                  <strong>{{ message.time }} </strong>
                </div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-card>
    </v-row>
  </v-container>
</template>
