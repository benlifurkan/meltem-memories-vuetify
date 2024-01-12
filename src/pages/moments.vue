<script lang="ts">
import { Toaster } from "vue-sonner";
import { authStore } from "@/store/auth";
import { ref, onMounted } from "vue";

export default {
  data: () => ({
    messages_1: [
      {
        time: "18:42pm",
        message: `Saçlarının rüzgarda uçuşmasını, içtiğin sigaranın dumanını, güldüğün zaman gözlerinin kapanmasını, kahkahalarını, konuşurken yaptığın mimikleri, kısacası her şeyini ilk kez gördüğüm gün.`,
        color: "green-lighten-1",
      },
    ],

    messages_2: [
      {
        time: "07:06am",
        message: `O gece seninle sabaha kadar film izleyip sohbet ettik. Kolyenin fotoğrafını çekmek için izin istedim ve sen de kabul ettin. O geceden kalan tek fotoğraf bu.`,
        color: "purple-lighten-1",
      },
    ],
  }),
};
</script>

<template>
  <v-container>
    <v-row justify="space-around">
      <v-card class="mb-8" width="200" height="500px">
        <v-img
          height="175"
          src="/public/moments/card-image-1.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">6 Mayıs 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_1"
              :key="message.time"
              :dot-color="message.color"
              size="12"
            >
              <div class="mt-0">
                <div class="font-weight-bold mb-2">
                  <strong>@{{ message.time }}</strong>
                </div>
                <div class="mb-2">{{ message.message }}</div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-card>

      <v-card class="mb-8" width="200" height="500px">
        <v-img
          height="175"
          src="/public/moments/card-image-2.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">7 Mayıs 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_2"
              :key="message.time"
              :dot-color="message.color"
              size="12"
            >
              <div class="mt-2">
                <div class="font-weight-bold mb-2">
                  <strong>@{{ message.time }}</strong>
                </div>
                <div class="mb-2">{{ message.message }}</div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-card>
    </v-row>
  </v-container>
</template>
