<template>
    <v-card>
        <v-toolbar
            :color="isDarkTheme ? 'blue darken-3': 'grey darken-4'"
            dark
            rounded
            
        >
            <v-tabs centered grow>
            <v-tab href="#search">
                Usługi
            </v-tab>
            <v-tab-item value="search">
                <ClientDataU/>
            </v-tab-item>

            <v-tab href="#rare">
                Pracownicy
            </v-tab>
            <v-tab-item value="rare">
                <ClientDataP />
            </v-tab-item>

            <v-tab href="#review">
                Dostawy
            </v-tab>
            <v-tab-item value="review">
                <ClientDataD/>
            </v-tab-item>
            </v-tabs>
        </v-toolbar>
    </v-card>
</template>
<script>
import {isDarkTheme} from '../mixins/isDarkTheme';
export default {
  mixins: [isDarkTheme],
  components: {
    "ClientDataU": () => import('./ClientDataU'),
    "ClientDataP": () => import('./ClientDataP'),
    "ClientDataD": () => import('./ClientDataD'),
  },
  data: () => ({
    tab: null,
    items: ['Pracownicy', 'Usługi', 'Podsumowanie',],
}),
};
</script>