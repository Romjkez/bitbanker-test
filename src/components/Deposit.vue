<template>
  <div class="d-flex justify-center">
    <div class="form-wrapper">
      <v-row>
        <v-col class="d-flex justify-center pa-0">
          <v-select
              class="form-control wallet-control"
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
              class="form-control"
              :append-icon="'mdi-chevron-down'"
              :items="currencyOptions"
              label="Choose currency"
              solo
          ></v-select>
        </v-col>
      </v-row>
      <v-row class="wallet-info">
        <v-col class="d-flex justify-center pa-0" cols="12">
          <v-img :src="require('../assets/qr.png')" max-width="119" max-height="112"/>
        </v-col>
        <v-col class="d-flex justify-center pa-0" cols="12">
          <p>FGBfvcnkfdnvkk74365832ybvcvdfvfvb</p>
        </v-col>
      </v-row>
      <v-row>
        <v-col class="d-flex justify-center pa-0">
          <v-btn class="copy-btn" elevation="0" x-large color="primary">Copy</v-btn>
        </v-col>
      </v-row>
    </div>
  </div>
</template>

<style>

.wallet-control {
  margin-top: 41px !important;
}

.wallet-info {
  margin-top: 37px !important;
}

.copy-btn {
  width: 100%;
  max-height: 50px;
  margin-top: 5px;
  margin-bottom: 40px;
}
</style>

<script>
export default {

  name: 'Deposit',
  data: () => ({
    isOverlayVisible: true,
    walletsOptions: ['Kraken', 'Parrot', 'Whale'],
    currencyOptions: ['BTC', 'ETH', 'USDT'],
  }),
}
</script>

