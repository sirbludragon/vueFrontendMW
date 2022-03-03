<template>
  <v-card >
    <v-toolbar :color="isDarkTheme ? 'blue darken-3' : 'grey darken-4'" dark flat>
      <v-toolbar-title> Dane Magazynu </v-toolbar-title>
    </v-toolbar>
    <v-card-text>
      <v-container>
        <v-row>
        <v-col cols="12" sm="6" md="4">
            <v-text-field
              :value="processData.resupplyRequest.warehouse.name"
              label="Nazwa Magazynu"
              outlined
              readonly
            ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="4">
            <v-text-field
              :value="processData.resupplyRequest.warehouse.voivodeship"
              label="Województwo"
              outlined
              readonly
            ></v-text-field>
        </v-col>
                <v-col cols="12" sm="6" md="4">
            <v-text-field
              :value="processData.resupplyRequest.warehouse.district"
              label="Powiat"
              outlined
              readonly
            ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="4">
            <v-text-field
              :value="processData.resupplyRequest.warehouse.city"
              label="Nazwa Magazynu"
              outlined
              readonly
            ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="4">
            <v-text-field
              :value="processData.resupplyRequest.warehouse.street"
              label="Województwo"
              outlined
              readonly
            ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="4">
            <v-text-field
              :value="processData.resupplyRequest.warehouse.warehouseId"
              label="Powiat"
              outlined
              readonly
            ></v-text-field>
        </v-col>
        </v-row>
        <v-card-actions >
          <v-btn absolute right top @click="openDetails">Szczegóły</v-btn>
        </v-card-actions>
      </v-container>
    </v-card-text>
    <ClientDataDetails v-model="dialog" v-if="dialogInitialized" />
  </v-card>
</template>
<script>
import { isDarkTheme } from '../mixins/isDarkTheme';
//import axios from 'axios';

export default {
  mixins: [isDarkTheme],
  components: {
    ClientDataDetails: () => import('./ClientDataDetails')
  },
  mounted() {
    this.context = window.coachViewContext;
    this.initData();
  },
  data: () => ({
    processData: {},
    context: null,
    // client: {
    //   name: 'przykladowe imie',
    //   surname: 'przykladowe nazwisko'
    // },
    dialog: false,
    dialogInitialized: false
  }),
  watch: {
    isDarkTheme() {
      console.log('Zmienił się isDarkTheme', this.isDarkTheme);
    }
  },
  methods: {
    openDetails() {
      this.dialogInitialized = true;
      this.dialog = true;
    },
    initData() {
      this.processData = this.context.binding.get('value');
    },
  },
};

</script>

<style>
.clientData {
  font-size: 20px;
}
</style>
