<script lang="ts" setup>
import { useQRCode } from "@vueuse/integrations/useQRCode";
import { Toaster } from "vue-sonner";
import { authStore } from "@/store/auth";
import { ref, onMounted } from "vue";

const sidebar = ref(false);
const link = ref("");
const qrCode = useQRCode(link, {
  margin: 0,
});

onMounted(() => {
  link.value = location.origin;
});
</script>

<template>
  <VLayout>
    <VApp class="bg-white">
      <VAppBar class="bg-white" v-if="$vuetify.display.mdAndUp" flat border>
        <template #prepend>
          <VBtn
            to="/"
            prepend-icon="mdi-heart"
            color="error"
            variant="tonal"
            class="rounded-xl"
          >
            <span class="text-xs">Geçmiş Olsun Bal Eşim</span>
          </VBtn>
        </template>

        <div class="d-flex align-center">
          <VBtn to="/" class="mr-2"> Ana Sayfa </VBtn>
          <VBtn to="/moments"> Anılarımız </VBtn>
        </div>

        <template #append>
          <VBtn
            icon
            href="tel:05382238288"
            size="small"
            variant="tonal"
            color="primary"
            class="ml-2"
            target="_blank"
          >
            <VIcon icon="mdi-phone" />
          </VBtn>
          <VBtn
            icon
            href="https://www.instagram.com/furkanbenli.dev/"
            size="small"
            variant="tonal"
            color="primary"
            class="ml-2"
            target="_blank"
          >
            <VIcon icon="mdi-instagram" />
          </VBtn>
          <VBtn
            icon
            href="https://twitter.com/furkanbenli_dev"
            size="small"
            variant="tonal"
            color="primary"
            class="ml-2"
            target="_blank"
          >
            <VIcon icon="mdi-twitter" />
          </VBtn>
          <VBtn
            icon
            href="https://github.com/benlifurkan"
            size="small"
            variant="tonal"
            color="primary"
            class="ml-2"
            target="_blank"
          >
            <VIcon icon="mdi-github" />
          </VBtn>
        </template>
      </VAppBar>

      <VAppBar v-else flat border>
        <template #prepend>
          <RouterLink
            to="/"
            class="text-white bg-error px-4 py-2 rounded-xl sm text-decoration-none"
            variant="accent"
          >
            <VIcon icon="mdi-needle" class="mr-2" />
            <span class="text-xs">KanKa</span>
          </RouterLink>
        </template>

        <template #append>
          <VBtn icon>
            <VIcon icon="mdi-menu" @click="sidebar = !sidebar" />
          </VBtn>
        </template>
      </VAppBar>

      <VNavigationDrawer v-model="sidebar" temporary floating>
        <VList>
          <VListItem
            prepend-icon="mdi-home"
            title="Kan Bağışı Takibi"
            to="/"
            link
          />
          <VListItem
            prepend-icon="mdi-image-album"
            to="/panel"
            title="Bağış Merkezi"
          />
        </VList>
      </VNavigationDrawer>

      <VMain class="my-4">
        <VContainer>
          <RouterView />
        </VContainer>
      </VMain>

      <VFooter
        style="margin-top: 120px; background-color: #f3f4f6"
        class="d-flex flex-column gap-4 bg-white"
      >
        <VContainer>
          <div
            class="d-flex flex-column-reverse align-center align-md-start flex-md-row"
          ></div>

          <div
            class="d-flex flex-wrap align-center justify-md-space-between justify-center"
          >
            <span class="d-block mt-4" style="color: #6b7280">
              © {{ new Date().getFullYear() }} - Tüm hakları saklıdır - Furkan
              Benli
            </span>

            <div class="d-flex align-center gap-4 mt-4">
              <VBtn
                icon
                href="tel:05382238288"
                size="small"
                variant="text"
                target="_blank"
              >
                <VIcon icon="mdi-phone" />
              </VBtn>
              <VBtn
                icon
                size="small"
                variant="text"
                href="https://instagram.com/furkanbenli.dev/"
                target="_blank"
              >
                <VIcon icon="mdi-instagram" />
              </VBtn>

              <VBtn
                icon
                size="small"
                variant="text"
                href="https://twitter.com/furkanbenli_dev"
                target="_blank"
              >
                <VIcon icon="mdi-twitter" />
              </VBtn>

              <VBtn
                icon
                size="small"
                variant="text"
                href="https://github.com/benlifurkan"
                target="_blank"
              >
                <VIcon icon="mdi-github" />
              </VBtn>
            </div>
          </div>
        </VContainer>
      </VFooter>
    </VApp>

    <Toaster rich-colors />
  </VLayout>
</template>
