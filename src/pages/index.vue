<script lang="ts" setup>
import { useFetch } from "@vueuse/core";
import { computed } from "vue";
import slugify from "slugify";
import { toast } from "vue-sonner";
import { s } from "unplugin-vue-router/dist/defineLoader-bde635fd";
import { time } from "console";

const images = [
  "kanka_1.jpg",
  "kanka_2.jpg",
  "kanka_3.jpg",
  "kanka_4.jpg",
  "kanka_5.jpg",
];
</script>

<template>
  <VRow>
    <VCol cols="12">
      <VCarousel
        cycle
        hide-delimiter-background
        show-arrows="hover"
        class="rounded-lg"
        :height="$vuetify.display.smAndDown ? 200 : 475"
        color="white"
      >
        <VCarouselItem
          v-for="image in images"
          :key="image"
          :src="`/slider/${image}`"
          cover
        />
      </VCarousel>
    </VCol>
  </VRow>
</template>
