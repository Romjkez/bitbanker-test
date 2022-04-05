<template>
  <div class="d-flex justify-center">
    <div class="form-wrapper">
      <v-row class="from-label label-wrapper">
        <v-col class="d-flex form-label">
          <span>From</span>
        </v-col>
      </v-row>
      <v-row>
        <v-col class="d-flex justify-center pa-0">
          <v-select
              class="form-control"
              :append-icon="'mdi-chevron-down'"
              :items="fromOptions"
              label="Choose exchange"
              solo
          ></v-select>
        </v-col>
      </v-row>
      <v-row class="label-wrapper to-label">
        <v-col class="d-flex form-label">
          <span>To</span>
        </v-col>
      </v-row>
      <v-row>
        <v-col class="d-flex justify-center pa-0">
          <v-select
              class="form-control"
              :append-icon="'mdi-chevron-down'"
              :items="toOptions"
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
          <v-text-field solo class="form-control amount" v-model="amount">
          </v-text-field>
        </v-col>
      </v-row>
      <v-card class="info-card">
        <div class="balance-card">
          Balance: 0.04763864
        </div>
        <div class="actions-buttons">
          <v-btn class="action-btn" color="label" elevation="0">10%</v-btn>
          <v-btn class="action-btn" color="label" elevation="0">25%</v-btn>
          <v-btn class="action-btn" color="label" elevation="0">50%</v-btn>
          <v-btn class="action-btn" color="label" elevation="0">100%</v-btn>
          <v-btn class="action-btn" color="label" elevation="0">Split</v-btn>
        </div>
      </v-card>
    </div>
  </div>
</template>

<style>

.from-label {
  margin-top: 41px !important;
}

.to-label {
  margin-top: 4px !important;
}

.form-label {
  padding-bottom: 10px;
}

.form-label span {
  margin-left: 15px;
}

.info-card {
  padding: 20px;
  box-shadow: 0 7px 16px rgba(60, 72, 76, 0.1) !important;
}

.form-control.amount {
  margin-bottom: 10px !important;
}

.form-control.amount .v-input__slot {
  margin-bottom: 0 !important;
}

.balance-card {
  color: var(--v-primary-base);
  padding: 8px;
  background-color: rgba(42, 101, 145, 0.1);
  font-size: 12px;
  width: fit-content;
  border-radius: 3px;
}

.actions-buttons {
  margin-top: 10px;
  display: flex;
  gap: 10px;
}

.action-btn {
  color: var(--v-white-base) !important;
  padding-left: 10px !important;
  padding-right: 10px !important;
  font-size: 12px !important;
  min-width: auto !important;
}


</style>

<script>
export default {

  name: 'Rebalance',
  data: () => ({
    fromOptions: ['Anonymous', 'Kitty'],
    toOptions: ['Warrior', 'Boxer'],
    currencyOptions: ['BTC', 'ETH', 'USDT'],
    amount: 2,
  }),
}
</script>
