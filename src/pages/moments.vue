<script lang="ts">
import { Toaster } from "vue-sonner";
import { authStore } from "@/store/auth";
import { ref, onMounted } from "vue";

export default {
  data: () => ({
    messages: [
      {
        from: "You",
        message: `Sure, I'll see you later.`,
        time: "10:42am",
        color: "deep-purple-lighten-1",
      },
      {
        from: "John Doe",
        message: "Yeah, sure. Does 1:00pm work?",
        time: "10:37am",
        color: "green",
      },
      {
        from: "You",
        message: "Did you still want to grab lunch today?",
        time: "9:47am",
        color: "deep-purple-lighten-1",
      },
    ],
  }),
};
</script>

<template>
  <v-container>
    <v-row justify="space-around">
      <v-card width="400">
        <v-img
          height="200"
          src="https://cdn.discordapp.com/attachments/1175828283598848000/1193350390356394024/hello-kity-kolye.jpg?ex=65ac6528&is=6599f028&hm=fe6df89ab5769ba26ab4c69c13e049d3a15a715a885666a146a632040bbdce5e&"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold ms-1 mb-2">7 Mayıs 2023</div>

          <v-timeline density="compact" align="start">
            <v-timeline-item
              v-for="message in messages"
              :key="message.time"
              :dot-color="message.color"
              size="x-small"
            >
              <div class="mb-4">
                <div class="font-weight-normal">
                  <strong>{{ message.from }}</strong> @{{ message.time }}
                </div>
                <div>{{ message.message }}</div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-card>
    </v-row>
  </v-container>
</template>
