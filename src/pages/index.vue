<script lang="ts" setup>
import { useFetch } from "@vueuse/core";
import { computed } from "vue";
import slugify from "slugify";
import { toast } from "vue-sonner";
import { s } from "unplugin-vue-router/dist/defineLoader-bde635fd";
import { time } from "console";

const images = [
  "meltem-1.jpg",
  "meltem-2.jpg",
  "meltem-3.jpg",
  "meltem-4.jpg",
  "meltem-5.jpg",
  "meltem-6.jpg",
  "meltem-7.jpg",
  "meltem-8.jpg",
  "meltem-9.jpg",
  "meltem-10.jpg",
];
</script>

<template>
  <VRow>
    <VCol cols="12">
      <VCarousel
        cycle
        hide-delimiter-background
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
