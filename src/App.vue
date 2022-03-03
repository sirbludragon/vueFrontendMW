<template> 
  <v-app :style="{background: $vuetify.theme.themes[theme].background}">
    <v-app-bar
      app
      color="primary"
    >
      <div class="d-flex align-center">
       
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          :src="this.$vuetify.theme.dark ? 'https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png' : 'https://cdn.vuetifyjs.com/images/logos/vuetify-name-light.png'"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>
      <v-icon>{{ this.$vuetify.theme.dark ? 'DARK' : 'LIGHT' }}</v-icon>
      <DarkTheme />
    </v-app-bar>
    <v-main>
      <v-container>
        <v-container>
        <ClientData/>
         </v-container>
      </v-container>
      <v-container>
        <ComponentPicker/>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
//`import ClientData from './components/ClientData';
import DarkTheme from './components/DarkTheme';
import ComponentPicker from './components/ComponentPicker';



export default {
  name: 'App',
  components: {
    ClientData:()=>import (/* webpackChunkName: "ClientData" */ './components/ClientData.vue'),
    DarkTheme,
    ComponentPicker,
  },
  computed:{
    theme(){
      return (this.$vuetify.theme.dark) ? 'dark' : 'light'
    }
  },
  data: () => ({
    drawer: null,
  }),
};
</script>