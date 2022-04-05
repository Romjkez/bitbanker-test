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
                <Deposit v-if="activeTab===0"/>
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


</style>

<script>
import Deposit from "@/components/Deposit";

export default {

  name: 'Main',
  components: {Deposit},
  data: () => ({
    isOverlayVisible: true,
    activeTab: 0,
  }),
}
</script>
