<template>
    <v-card>
        <v-toolbar
            :color="isDarkTheme ? 'blue darken-3': 'grey darken-4'"
            dark
            rounded
            
        >
            <v-tabs centered grow>
            <v-tab href="#ClientDataU">
                Usługi
            </v-tab>
            <v-tab-item value="ClientDataU">
                <ClientDataU/>
            </v-tab-item>

            <v-tab href="#ClientDataP">
                Pracownicy
            </v-tab>
            <v-tab-item value="ClientDataP">
                <ClientDataP />
            </v-tab-item>

            <v-tab href="#ClientDataD">
                Dostawy
            </v-tab>
            <v-tab-item value="ClientDataD">
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