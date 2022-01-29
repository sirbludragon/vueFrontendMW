<template> 
  <v-app>
    <v-app-bar
      app
      color="primary"
    >
      <div class="d-flex align-center">
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
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
        <ClientData/>
      </v-container>
      <v-container>
        
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import ClientData from './components/ClientData';
import DarkTheme from './components/DarkTheme';



export default {
  name: 'App',
  components: {
    ClientData,
    DarkTheme
  },
  data: () => ({
    img_src:  ['https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png', 'https://cdn.vuetifyjs.com/images/logos/vuetify-name-light.png']
  }),
};
</script>
