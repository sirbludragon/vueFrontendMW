<template>
    <v-container>
    <v-card>
    <v-toolbar :color="isDarkTheme ? 'blue darken-3' : 'grey darken-4'" dark flat >
      <v-tabs v-model="tab"  grow flat>
        <v-tab v-for="item in items" :key="item.tab">
          {{ item.tab }}
        </v-tab>
      </v-tabs>
      </v-toolbar>
      <v-tabs-items v-model="tab" >
        <v-tab-item v-for="item in items" :key="item.tab">
          <v-card flat>
            <v-card-text>
              <component v-bind:is="item.content"></component>
            </v-card-text>
          </v-card>
        </v-tab-item>
      </v-tabs-items>
    </v-card>
  </v-container>
</template>
<script>
import {isDarkTheme} from '../mixins/isDarkTheme';
export default {
  mixins: [isDarkTheme],
  components: {
    "ClientDataP": () => import('./ClientDataP'),
    "ClientDataD": () => import('./ClientDataD'),
  },
  data: () => ({
    tab: null,
    items: [
        { tab: 'Dane Zamawiającego', content: 'ClientDataP' },
        { tab: 'Zamówienie', content: 'ClientDataD' }
    ],
}),
};
</script>