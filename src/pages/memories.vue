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
        color: "blue-lighten-1",
      },
    ],

    messages_2: [
      {
        location: "Akyazı/Sakarya",
        time: "07:06am",
        message: `O gece seninle sabaha kadar film izleyip sohbet ettik. Kolyenin fotoğrafını çekmek için izin istedim ve sen de kabul ettin. O geceden kalan tek fotoğraf bu.`,
        color: "blue-lighten-1",
      },
    ],

    messages_3: [
      {
        location: "Akyazı/Sakarya",
        time: "15:40pm",
        message: `O gün seninle ilk kez bir parka gidip oturduk. Seninle ilk kez bir şeyler yaptık. Seninle ilk kez garip şeyler hissettik. Seni ilk kez öptüm. Bu hisler benim için çok yeniydi. Bu güzel hisleri ilk kez senin gibi mükemmel biriyle yaşadığım için çok şanslıyım.`,
        color: "blue-lighten-1",
      },
    ],

    messages_4: [
      {
        location: "Akyazı/Sakarya",
        time: "17:13pm",
        message: `Senden kilometrelerce uzakta olmama rağmen, doğum günün için güzel bir şeyler yapmam gerekiyordu. Bu yüzden sana hayatın boyunca unutamayacağın bir sürpriz hazırladım. İlk defa birinin doğum günü için bu kadar çaba sarfettim.`,
        color: "blue-lighten-1",
      },
    ],

    messages_5: [
      {
        location: "Kahveci Hacıbaba Cafe Çankaya/Ankara",
        time: "17:53pm",
        message: `Uzun bir uzak mesafe ilişkisinden sonra o gün seninle ilk kez buluştuk. Sana sarılmayı, kokunu içime çekmeyi, ellerini tutmayı çok özlediğimi iliklerime kadar hissetmiştim. Uzun bir ayrılıktan sonra seni tekrar görmek bana çok iyi geldi. `,
        color: "blue-lighten-1",
      },
    ],

    messages_6: [
      {
        location: "ANKAmall AVM Yenimahalle/Ankara",
        time: "16:15pm",
        message: `O gün seninle ilk defa bir AVM'ye gittik, kahve içip sohbet ettik. Seninle zamanın çok çabuk geçtiği yetmezmiş gibi bir de güzel gözlerinin içinde kaybolup gitmiştim. Benim için çok güzel bir gündü.`,
        color: "blue-lighten-1",
      },
    ],

    messages_7: [
      {
        location: "Recep Tayyip Erdoğan Parkı Pursaklar/Ankara",
        time: "00:14am",
        message:
          "O gün seninle gecenin bir yarısı bir parka gidip oturduk. Dakikalarca dizlerime yatıp ağladın. Birinin ağlaması hiç bu kadar canımı acıtmamıştı. Ne kadar üzücü bir gece olsa da ikimiz de bir o kadar mutluyduk. Bu gece bizim ilk öpüştüğümüz geceydi.",
        color: "blue-lighten-1",
      },
    ],

    messages_8: [
      {
        location: "AŞTİ Otogarı Yenimahalle/Ankara",
        time: "18:02pm",
        message:
          "Mükemmel geçen iki günden sonra senden ayrılmanın vakti gelip çattı. Seni asla bırakmak istemesem de dönmek zorundayım. Sana son kez sarılmak canımı çok yakıyor. Umarım bir gün hep yan yana oluruz. Kendine iyi bak sevgilim. Seni çok özleyeceğim.",
        color: "blue-lighten-1",
      },
    ],

    messages_9: [
      {
        location: "Pursaklar/Ankara",
        time: "13:42pm",
        message:
          "Senden aldığım bu özel hediye, kalbimde unutulmaz bir iz bıraktı. Her bakışımda bu hediyeyi görmek, sevginin gücünü hatırlatıyor. Bu küçük armağan, en değerli anılarımızı içinde taşıyor ve benim için çok özel.",
        color: "blue-lighten-1",
      },
    ],

    messages_10: [
      {
        location: "Yıldırım/Bursa",
        time: "11:17am",
        message:
          "O gün sen yanımda yoksun diye üzerimde isminin yazılı olduğu bir t-shirt ile düğüne gitmiştim. Bunu gördüğünde yaşadığın mutluluk hala aklımdan çıkmıyor. Senin çocuk gibi mutlu olduğun her an benim için çok özel. Seni çocuk gibi mutlu etmenin verdiği keyif ise tarif edilemez.",
        color: "blue-lighten-1",
      },
    ],

    messages_11: [
      {
        location: "Akyazı Devlet Hastanesi Akyazı/Sakarya",
        time: "01.18am",
        message:
          "O gün çok hasta oldun. Seni böyle görmek canımdan can götürdü. Sen uyurken saatlerce başında bekledim, seni izledim. Üşümemen için üzerimdeki hırkayı çıkartıp üzerine örttüm. O gece bir şey farkettim sevgilim, seninle hastalık da güzel sağlık da...",
        color: "blue-lighten-1",
      },
    ],

    messages_12: [
      {
        location: "Akyazı/Sakarya",
        time: "22:05pm",
        message:
          "Sen gittikten sonra hastaneden aldığım barkodu cüzdanımda sakladım. Yanımda sana dair şeyler taşımak beni mutlu ediyor. Özel anlarımızı hatırlamak için bu küçük detaylar yeterli oluyor. Seni ve sana dair her detayı çok seviyorum.",
        color: "blue-lighten-1",
      },
    ],

    messages_13: [
      {
        location: "Vega AVM Subayevleri Altındağ/Ankara",
        time: "15:33pm",
        message:
          "Uzun bir ayrılığın ardından seninle tekrar buluştuk. Sen yanımdayken yediğim her yiyecek lezzetli, içtiğim her içecek nefismiş. Seninleyken çok şey öğrendim sevgilim, yapılan en basit aktiviteler bile çok özel anılara dönüşebilirmiş.",
        color: "blue-lighten-1",
      },
    ],

    messages_14: [
      {
        location: "Simit Sarayı Karanfil Çankaya/Ankara",
        time: "17:40pm",
        message:
          "Hiç anlamamama rağmen sana gloss sürdüm. Bu an sana ne hissettirdi bilmiyorum ama bana çok özel hissettirdi. En güzel şekilde yapabilmek için biraz çaba sarfetmiştim. Umarım güzel olmuştur.",
        color: "blue-lighten-1",
      },
    ],

    messages_15: [
      {
        location: "Simit Sarayı Karanfil Çankaya/Ankara",
        time: "17:59pm",
        message:
          "Seninle parmak güreşi oyunu oynadık. Bu oyunu oynarken bir şey öğrendim. Kaybedenin olmadığı oyunlar da varmış. Seninle oynadığım her oyun, kaybedeni olmayan bir oyunmuş.",
        color: "blue-lighten-1",
      },
    ],

    messages_16: [
      {
        location: "AŞTİ Otogarı Yenimahalle/Ankara",
        time: "18:43pm",
        message:
          "Yine ayrılık vakti geldi çattı. Bu seferki ayrılık çok daha zor. Her defasında sana tam alışmışken geri dönmek zorunda kalmaktan nefret ediyorum. Daha önce de söylediğim gibi, umarım bir gün hep yan yana oluruz. Kendine iyi bak sevgilim. Seni çok özleyeceğim.",
        color: "blue-lighten-1",
      },
    ],

    messages_17: [
      {
        location: "Pursaklar/Ankara",
        time: "14:12pm",
        message:
          "Sana harika bir dudak parlatıcısı aldım. Mutluluğun tarif edilemezdi. Bu dudak parlatıcısı en güzel günlerde hep dudaklarını parlatacak. Tıpkı senin benim hayatımı tam anlamıyla parlattığın gibi.",
        color: "blue-lighten-1",
      },
    ],

    messages_18: [
      {
        location: "Pursaklar/Ankara",
        time: "14:40pm",
        message:
          "Evine geldim, ailenle beraber kahvaltı yaptım. Bana yaptığınız doğum günü sürprizi beni gerçekten çok duygulandırdı. Umarım nice güzel yılları seninle, sizinle geçiririm. Teşekkür ederim sevgilim. Seni çok seviyorum.",
        color: "blue-lighten-1",
      },
    ],

    messages_19: [
      {
        location: "Akçakoca/Düzce",
        time: "03:54am",
        message:
          "Sabaha kadar Pico Park oynadık. Bölümleri geçmeye çalışmak, seninle vakit geçirmek harikaydı. Bölümü geçemediğimizde sinirlenmen beni daha da eğlendirdi diyebilirim. Bu oyunu oynayarak güzel anılarımıza, bir güzel anı daha kattık.",
        color: "blue-lighten-1",
      },
    ],

    messages_20: [
      {
        location: "Akçakoca/Düzce",
        time: "23:23pm",
        message:
          "Sana her şey için sonsuz teşekkür ederim sevgilim. Umarım bu anı defterine bir gün evliliğimizi de yazarız. Daha sonra çocuklarımızı, torunlarımızı da yazarız. Seninle mutlu bir aile kurmak için sabırsızlanıyorum. Sana harika bir eş, çocuklarımıza mükemmel bir baba olacağıma söz veriyorum. Seni çok seviyorum sevgilim.",
        color: "blue-lighten-1",
      },
    ],
  }),
};
</script>

<template>
  <v-container>
    <v-row justify="space-around">
      <v-card class="mb-8" width="270" height="550px">
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

      <v-card class="mb-8" width="270" height="550px">
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

      <v-card class="mb-8" width="270" height="550px">
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

      <v-card class="mb-8" width="270" height="550px">
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
      <v-card class="mb-8" width="270" height="550px">
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

      <v-card class="mb-8" width="270" height="550px">
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

      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-7.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">11 Haziran 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_7"
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

      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-8.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">11 Haziran 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_8"
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
      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-9.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">11 Haziran 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_9"
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

      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-10.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">1 Temmuz 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_10"
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

      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-11.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">30 Temmuz 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_11"
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

      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-12.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">30 Temmuz 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_12"
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
      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-13.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">8 Eylül 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_13"
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

      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-14.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">8 Eylül 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_14"
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

      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-15.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">8 Eylül 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_15"
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

      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-16.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">9 Eylül 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_16"
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
      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-17.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">9 Kasım 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_17"
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

      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-18.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">30 Aralık 2023</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_18"
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

      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-19.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <div class="font-weight-bold mb-2">3 Ocak 2024</div>

          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_19"
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

      <v-card class="mb-8" width="270" height="550px">
        <v-img
          height="175"
          src="/memories/card-image-20.png"
          cover
          class="text-white"
        >
        </v-img>

        <v-card-text>
          <v-timeline density="compact" align="center">
            <v-timeline-item
              v-for="message in messages_20"
              :key="message.time"
              :dot-color="message.color"
              size="12"
            >
              <div class="mt-0">
                <div class="font-weight-normal font-italic mb-2">
                  <VIcon
                    icon="mdi-infinity"
                    class="mr-1 text-red align-center rounded-xl"
                  />
                </div>
                <div class="font-weight-normal font-italic mb-2"></div>
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
