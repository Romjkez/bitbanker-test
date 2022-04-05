<template>
  <v-app>
    <v-container>
      <v-row>
        <v-col
            class="d-flex justify-center">
          <v-btn
              color="primary"
              @click="isOverlayVisible = true"
          >
            Show popup
          </v-btn>
          <v-overlay
              :dark="$vuetify.theme.dark"
              :absolute="true"
              :value="isOverlayVisible"
          >
            <v-card class="popup-card" color="white">
              <v-container style="padding: 0">
                <v-row>
                  <v-col>
                    <v-tabs v-model="activeTab">
                      <v-tab>Deposit</v-tab>
                      <v-tab>Withdraw</v-tab>
                      <v-tab>Rebalance</v-tab>
                    </v-tabs>
                  </v-col>
                  <v-col class="d-flex justify-end">
                    <v-btn
                        icon
                        raised
                        @click="isOverlayVisible = false"
                    >
                      <v-icon>mdi-close</v-icon>
                    </v-btn>
                  </v-col>
                </v-row>
                <div v-if="activeTab===0">
                  <v-row>
                    <v-col class="d-flex justify-center pa-0">
                      <v-select
                          class="deposit-form-control wallet-control"
                          :append-icon="'mdi-chevron-down'"
                          :items="walletsOptions"
                          :value="walletsOptions[0]"
                          label="Choose wallet"
                          solo
                      ></v-select>
                    </v-col>
                  </v-row>
                  <v-row>
                    <v-col class="d-flex justify-center pa-0">
                      <v-select
                          class="deposit-form-control"
                          :append-icon="'mdi-chevron-down'"
                          :items="currencyOptions"
                          label="Choose currency"
                          solo
                      ></v-select>
                    </v-col>
                  </v-row>
                  <v-row>
                    <v-col class="d-flex justify-center" cols="12">
                      <v-img :src="require('../assets/qr.png')" max-width="119" max-height="112"/>
                    </v-col>
                    <v-col class="d-flex justify-center" cols="12">
                      <p>FGBfvcnkfdnvkk74365832ybvcvdfvfvb</p>
                    </v-col>
                  </v-row>
                  <v-row>
                    <v-col class="d-flex justify-center">
                      <v-btn class="copy-btn" elevation="0" x-large color="primary">Copy</v-btn>
                    </v-col>
                  </v-row>
                </div>
                <div v-if="activeTab===1">
                  2
                </div>
                <div v-if="activeTab===2">
                  3
                </div>

              </v-container>

            </v-card>
          </v-overlay>
        </v-col>
      </v-row>
    </v-container>
  </v-app>


</template>

<style>
.popup-card {
  min-width: 780px;
  padding: 30px
}

.deposit-form-control {
  max-height: 50px;
  margin-bottom: 20px !important;
  max-width: 380px !important;
  border-radius: 5px !important;
}

.deposit-form-control .v-input__slot {
  box-shadow: none !important;
  background-color: var(--v-border-base) !important;
}

.wallet-control {
  margin-top: 41px !important;
}

.copy-btn {
  width: 378px;
  max-height: 50px;
  margin-top: 5px;
}

.copy-btn .v-btn__content {
  text-transform: none !important;
}

</style>

<script>
export default {

  name: 'Main',

  data: () => ({
    isOverlayVisible: true,
    walletsOptions: ['Kraken', 'Parrot', 'Whale'],
    currencyOptions: ['BTC', 'ETH', 'USDT'],
    activeTab: 0,
    qrPath: () => __dirname + 'assets/qr.png'
  }),
}
</script>
