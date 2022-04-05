<template>
  <div class="d-flex justify-center">
    <div class="form-wrapper">
      <v-row class="wallet-control">
        <v-col class="d-flex justify-center pa-0">
          <v-select
              class="form-control"
              :append-icon="'mdi-chevron-down'"
              :items="walletsOptions"
              label="Choose exchange"
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
      <v-row>
        <v-col class="d-flex justify-center pa-0">
          <v-text-field solo class="form-control">
            <v-btn slot="append">Max</v-btn>
          </v-text-field>
        </v-col>
      </v-row>
      <v-row>
        <v-col class="d-flex justify-center pa-0">
          <v-btn x-large color="primary" class="withdraw-btn">Withdraw</v-btn>
        </v-col>
      </v-row>
    </div>
  </div>
</template>

<style>
.wallet-control {
  margin-top: 41px !important;
}

.withdraw-btn {
  width: 100%;
  max-height: 50px;
  margin-top: 5px;
  margin-bottom: 40px;
}

</style>

<script>
export default {

  name: 'Withdraw',
  data: () => ({
    currencyOptions: ['BTC', 'ETH', 'USDT'],
    walletsOptions: ['Kraken', 'Parrot', 'Whale'],
  }),
}
</script>
