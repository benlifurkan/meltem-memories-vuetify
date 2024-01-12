<script lang="ts">
import { Toaster } from "vue-sonner";
import { authStore } from "@/store/auth";
import { ref, onMounted } from "vue";

export default {
  data: () => ({
    messages: [
      {
        time: "07:06am",
        message: `O gece seninle sabaha kadar film izleyip sohbet ettik. Kolyenin fotoğrafını çekmek için izin istedim ve sen de kabul ettin. O geceden kalan tek fotoğraf bu.`,
        color: "green-lighten-1",
      },
    ],
  }),
};
</script>

<template>
  <v-container>
    <v-row justify="space-around">
      <v-card width="200" height="500px">
        <v-img
          height="175"
          src="/public/moments/hello-kitty.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">7 Mayıs 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages"
              :key="message.time"
              :dot-color="message.color"
              size="15"
            >
              <div class="mt-2">
                <div class="font-weight-bold mb-2">
                  <strong>@{{ message.time }}</strong>
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
