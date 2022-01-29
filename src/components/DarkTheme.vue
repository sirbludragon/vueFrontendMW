<template>
  <v-btn icon @click="changeTheme">
    <v-icon>mdi-brightness-{{ this.isDarkTheme ? '4' : '7' }}</v-icon>
  </v-btn>
</template>

<script>
import {isDarkTheme} from '../mixins/isDarkTheme';
//import ClientDataVue from './ClientData.vue';

export default {
mixins: [isDarkTheme],
  mounted() {
      this.$store.dispatch('initTheme');
  },
  watch: {
      isDarkTheme(val) {
          this.darkTheme = val; 
          this.setTheme();
      }
  },
  methods: {
    changeTheme() {
        this.$store.commit('setDarkTheme', !this.isDarkTheme); 
        this.setTheme();
    },
    setTheme() {
        this.$vuetify.theme.dark = this.darkTheme;
        //ClientDataVue.$vuetify.theme.darkTheme = this.darkTheme;
    }
  }
};
</script>

<style></style>