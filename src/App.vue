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
            prepend-icon="mdi-needle"
            color="error"
            variant="tonal"
            class="rounded-xl"
          >
            <span class="text-xs">KanKa</span>
          </VBtn>
        </template>

        <div class="d-flex align-center">
          <VBtn to="/" class="mr-2"> Menüler </VBtn>
          <VBtn to="/contact"> İletişim </VBtn>
        </div>

        <template #append>
          <VBtn
            icon
            href="tel:05382238288"
            size="small"
            variant="tonal"
            color="primary"
            class="ml-2"
          >
            <VIcon icon="mdi-phone" />
          </VBtn>

          <VBtn
            v-if="!authStore.isLoggedIn"
            icon
            to="/panel/login"
            size="small"
            variant="tonal"
            color="primary"
            class="ml-2"
          >
            <VIcon icon="mdi-login" />
          </VBtn>

          <template v-else>
            <VBtn
              icon
              to="/panel/logout"
              size="small"
              variant="tonal"
              color="error"
              class="ml-2"
            >
              <VIcon icon="mdi-logout" />
            </VBtn>
          </template>
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
            prepend-icon="mdi-blood-bag"
            title="Kan Bağışı Takibi"
            to="/"
            link
          />
          <VListItem
            prepend-icon="mdi-needle"
            to="/panel"
            title="Bağış Merkezi"
          />
          <VListItem
            prepend-icon="mdi-format-list-checks"
            to="/panel"
            title="Bağış Talepleri"
          />
          <VListItem
            prepend-icon="mdi-phone"
            title="İletişim"
            to="/contact"
            link
          />

          <VListItem
            v-if="!authStore.isLoggedIn"
            prepend-icon="mdi-login"
            to="/panel/login"
            title="Giriş Yap"
          />

          <template v-else>
            <VListItem
              prepend-icon="mdi-logout"
              to="/panel/logout"
              title="Çıkış Yap"
            />
          </template>
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
              © {{ new Date().getFullYear() }} - Tüm hakları saklıdır - Hardal
            </span>

            <div class="d-flex align-center gap-4 mt-4">
              <VBtn
                icon
                size="small"
                variant="text"
                href="https://www.instagram.com/hardalburger/"
                target="_blank"
              >
                <VIcon icon="mdi-instagram" />
              </VBtn>

              <VBtn
                icon
                size="small"
                variant="text"
                href="https://www.facebook.com/people/Hardal/100039949007340/"
                target="_blank"
              >
                <VIcon icon="mdi-facebook" />
              </VBtn>

              <VBtn
                icon
                size="small"
                variant="text"
                href="https://www.twitter.com/hardalcafe"
                target="_blank"
              >
                <VIcon icon="mdi-twitter" />
              </VBtn>
            </div>
          </div>
        </VContainer>
      </VFooter>
    </VApp>

    <Toaster rich-colors />
  </VLayout>
</template>
