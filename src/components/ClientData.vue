<template>
  <v-card flat>
     <v-toolbar
      :color="isDarkTheme ? 'blue darken-3': 'grey darken-4'"
      dark
      flat
    >
      <v-toolbar-title>
        Dane klienta
      </v-toolbar-title>
    </v-toolbar>
    <v-card-text
      ><span><b>Imię: </b>{{ client.name }}</span
      ><br />
      <span><b>Nazwisko: </b>{{ client.surname }}</span></v-card-text
    >
    <v-btn absolute right top @click="openDetails">Szczegóły</v-btn>
    <ClientDataDetails v-model="dialog" v-if="dialogInitialized" />
  </v-card>
</template>
<script>
import {isDarkTheme} from '../mixins/isDarkTheme';
export default {
  mixins: [isDarkTheme],
  components: {
    "ClientDataDetails": () => import('./ClientDataDetails'),
  },
  data: () => ({
    client: {
      name: 'przykladowe imie',
      surname: 'przykladowe nazwisko'
    },
    dialog: false,
    dialogInitialized: false
  }),
  watch: {
    isDarkTheme() {
      console.log("Zmienił się isDarkTheme", this.isDarkTheme);
    }
  },
  methods: {
    openDetails() {
      this.dialogInitialized = true;
      this.dialog = true
    }
  },
};
</script>

<style>
.clientData {
  font-size: 20px;
}
</style>