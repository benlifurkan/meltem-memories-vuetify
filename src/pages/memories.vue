<script lang="ts">
import { Toaster } from "vue-sonner";
import { authStore } from "@/store/auth";
import { ref, onMounted } from "vue";

export default {
  data: () => ({
    messages_1: [
      {
        location: "Akyazı/Sakarya",
        time: "18:42pm",
        message: `Saçlarının rüzgarda uçuşmasını, içtiğin sigaranın dumanını, güldüğün zaman gözlerinin kapanmasını, kahkahalarını, konuşurken yaptığın mimikleri, kısacası her şeyini ilk kez gördüğüm gün.`,
        color: "green-lighten-1",
      },
    ],

    messages_2: [
      {
        location: "Akyazı/Sakarya",
        time: "07:06am",
        message: `O gece seninle sabaha kadar film izleyip sohbet ettik. Kolyenin fotoğrafını çekmek için izin istedim ve sen de kabul ettin. O geceden kalan tek fotoğraf bu.`,
        color: "purple-lighten-1",
      },
    ],

    messages_3: [
      {
        location: "Akyazı/Sakarya",
        time: "15:40pm",
        message: `O gün seninle ilk kez bir parka gidip oturduk. Seninle ilk kez bir şeyler yaptık. Seninle ilk kez garip şeyler hissettik. Seni ilk kez öptüm. Bu hisler benim için çok yeniydi. Bu güzel hisleri ilk kez senin gibi mükemmel biriyle yaşadığım için çok şanslıyım.`,
        color: "pink-lighten-1",
      },
    ],

    messages_4: [
      {
        location: "Akyazı/Sakarya",
        time: "17:13pm",
        message: `Senden kilometrelerce uzakta olmama rağmen, doğum günün için güzel bir şeyler yapmam gerekiyordu. Bu yüzden sana hayatın boyunca unutamayacağın bir sürpriz hazırladım. İlk defa birinin doğum günü için bu kadar çaba sarfettim.`,
        color: "yellow-lighten-1",
      },
    ],

    messages_5: [
      {
        location: "Kahveci Hacıbaba Cafe Çankaya/Ankara",
        time: "17:53pm",
        message: `Uzun bir uzak mesafe ilişkisinden sonra o gün seninle ilk kez buluştuk. Sana sarılmayı, kokunu içime çekmeyi, ellerini tutmayı çok özlediğimi iliklerime kadar hissetmiştim. Uzun bir ayrılıktan sonra seni tekrar görmek bana çok iyi geldi. `,
        color: "yellow-lighten-1",
      },
    ],

    messages_6: [
      {
        location: "ANKAmall AVM Yenimahalle/Ankara",
        time: "17:53pm",
        message: `Uzun bir uzak mesafe ilişkisinden sonra o gün seninle ilk kez buluştuk. Sana sarılmayı, kokunu içime çekmeyi, ellerini tutmayı çok özlediğimi iliklerime kadar hissetmiştim. Uzun bir ayrılıktan sonra seni tekrar görmek bana çok iyi geldi. `,
        color: "blue-lighten-1",
      },
    ],
  }),
};
</script>

<template>
  <v-container>
    <v-row justify="space-around">
      <v-card class="mb-8" width="250" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-1.png"
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
              :location="message.location"
              :dot-color="message.color"
              size="12"
            >
              <div class="mt-0">
                <div class="font-weight-normal font-italic mb-2">
                  <VIcon
                    icon="mdi-map-marker"
                    class="mr-1 text-blue align-center rounded-xl"
                  />
                  <strong class="ml-0 text-xs pt-2 align-center">{{
                    message.location
                  }}</strong>
                </div>
                <div class="font-weight-bold mb-2">
                  <strong>@{{ message.time }}</strong>
                </div>
                <div class="mb-2">{{ message.message }}</div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-card>

      <v-card class="mb-8" width="250" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-2.png"
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
              :location="message.location"
              :dot-color="message.color"
              size="12"
            >
              <div class="mt-0">
                <div class="font-weight-normal font-italic mb-2">
                  <VIcon
                    icon="mdi-map-marker"
                    class="mr-1 text-blue align-center rounded-xl"
                  />
                  <strong class="ml-0 text-xs pt-2 align-center">{{
                    message.location
                  }}</strong>
                </div>
                <div class="font-weight-bold mb-2">
                  <strong>@{{ message.time }}</strong>
                </div>
                <div class="mb-2">{{ message.message }}</div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-card>

      <v-card class="mb-8" width="250" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-3.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">7 Mayıs 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_3"
              :key="message.time"
              :location="message.location"
              :dot-color="message.color"
              size="12"
            >
              <div class="mt-0">
                <div class="font-weight-normal font-italic mb-2">
                  <VIcon
                    icon="mdi-map-marker"
                    class="mr-1 text-blue align-center rounded-xl"
                  />
                  <strong class="ml-0 text-xs pt-2 align-center">{{
                    message.location
                  }}</strong>
                </div>
                <div class="font-weight-bold mb-2">
                  <strong>@{{ message.time }}</strong>
                </div>
                <div class="mb-2">{{ message.message }}</div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-card>

      <v-card class="mb-8" width="250" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-4.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">17 Mayıs 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_4"
              :key="message.time"
              :location="message.location"
              :dot-color="message.color"
              size="12"
            >
              <div class="mt-0">
                <div class="font-weight-normal font-italic mb-2">
                  <VIcon
                    icon="mdi-map-marker"
                    class="mr-1 text-blue align-center rounded-xl"
                  />
                  <strong class="ml-0 text-xs pt-2 align-center">{{
                    message.location
                  }}</strong>
                </div>
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

    <v-row justify="space-around">
      <v-card class="mb-8" width="250" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-5.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">9 Haziran 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_5"
              :key="message.time"
              :location="message.location"
              :dot-color="message.color"
              size="12"
            >
              <div class="mt-0">
                <div class="font-weight-normal font-italic mb-2">
                  <VIcon
                    icon="mdi-map-marker"
                    class="mr-1 text-blue align-center rounded-xl"
                  />
                  <strong class="ml-0 text-xs pt-2 align-center">{{
                    message.location
                  }}</strong>
                </div>
                <div class="font-weight-bold mb-2">
                  <strong>@{{ message.time }}</strong>
                </div>
                <div class="mb-2">{{ message.message }}</div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-card>

      <v-card class="mb-8" width="250" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-6.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">9 Haziran 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_6"
              :key="message.time"
              :location="message.location"
              :dot-color="message.color"
              size="12"
            >
              <div class="mt-0">
                <div class="font-weight-normal font-italic mb-2">
                  <VIcon
                    icon="mdi-map-marker"
                    class="mr-1 text-blue align-center rounded-xl"
                  />
                  <strong class="ml-0 text-xs pt-2 align-center">{{
                    message.location
                  }}</strong>
                </div>
                <div class="font-weight-bold mb-2">
                  <strong>@{{ message.time }}</strong>
                </div>
                <div class="mb-2">{{ message.message }}</div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-card>

      <v-card class="mb-8" width="250" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-3.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">7 Mayıs 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_6"
              :key="message.time"
              :location="message.location"
              :dot-color="message.color"
              size="12"
            >
              <div class="mt-0">
                <div class="font-weight-normal font-italic mb-2">
                  <VIcon
                    icon="mdi-map-marker"
                    class="mr-1 text-blue align-center rounded-xl"
                  />
                  <strong class="ml-0 text-xs pt-2 align-center">{{
                    message.location
                  }}</strong>
                </div>
                <div class="font-weight-bold mb-2">
                  <strong>@{{ message.time }}</strong>
                </div>
                <div class="mb-2">{{ message.message }}</div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-card-text>
      </v-card>

      <v-card class="mb-8" width="250" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-4.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">17 Mayıs 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_1"
              :key="message.time"
              :location="message.location"
              :dot-color="message.color"
              size="12"
            >
              <div class="mt-0">
                <div class="font-weight-normal font-italic mb-2">
                  <VIcon
                    icon="mdi-map-marker"
                    class="mr-1 text-blue align-center rounded-xl"
                  />
                  <strong class="ml-0 text-xs pt-2 align-center">{{
                    message.location
                  }}</strong>
                </div>
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
