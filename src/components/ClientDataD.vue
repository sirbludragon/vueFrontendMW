<template>
        <v-card flat>
        <v-card-title>
            Produkty zamówienia
            <v-spacer></v-spacer>
            <v-text-field
            v-model="search"
            append-icon="mdi-magnify"
            label="Search"
            single-line
            hide-details
            ></v-text-field>
        </v-card-title>
        <v-data-table
            :headers="headers"
            :items="processData.resupplyRequest.itemList.items"
            :search="search"
        ></v-data-table>
                <v-container>
            <v-card-actions >
            <v-btn block x-large color="success" @click="save"> Wyślij  </v-btn>
            </v-card-actions>
        </v-container>
        </v-card>
</template>
<script>
export default {
    mounted() {
        this.context = window.coachViewContext;
        this.initData();
    },
    data: () => ({
    processData: {},
    search: '',
    headers: [
        {
          text: 'Nazwa produktu',
          align: 'start',
          sortable: true,
          value: 'name',
        },
        { text: 'Ilość', value: 'quantity' },
        { text: 'Cena za sztukę', value: 'unitPrice' },
        { text: 'Razem', value: 'totalPrice' },
    ]
    }),
    methods: {
        initData() {
            this.processData = this.context.binding.get('value');
        },
        save(){
            this.context.binding.set("value",this.processData);
            this.context.trigger();
        }
    },
};
</script>