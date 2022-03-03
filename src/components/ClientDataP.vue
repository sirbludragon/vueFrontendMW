<template>
        <v-card flat>
        <v-container>
        <v-container>
        <v-row>
        <v-col cols="12" sm="6" md="4">
            <v-text-field
              :value="processData.resupplyRequest.shopData.name"
              label="Nazwa Magazynu"
              outlined
              readonly
            ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="4">
            <v-text-field
              :value="processData.resupplyRequest.shopData.voivodeship"
              label="Województwo"
              outlined
              readonly
            ></v-text-field>
        </v-col>
                <v-col cols="12" sm="6" md="4">
            <v-text-field
              :value="processData.resupplyRequest.shopData.district"
              label="Powiat"
              outlined
              readonly
            ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="4">
            <v-text-field
              :value="processData.resupplyRequest.shopData.city"
              label="Nazwa Magazynu"
              outlined
              readonly
            ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="4">
            <v-text-field
              :value="processData.resupplyRequest.shopData.street"
              label="Województwo"
              outlined
              readonly
            ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="4">
            <v-text-field
              :value="processData.resupplyRequest.shopData.shopId"
              label="Powiat"
              outlined
              readonly
            ></v-text-field>
        </v-col>
                <v-col cols="12" sm="6" md="6">
            <v-text-field
              :value="processData.resupplyRequest.purchaserData.fullName"
              label="Nazwa Magazynu"
              outlined
              readonly
            ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="6">
            <v-text-field
              :value="processData.resupplyRequest.purchaserData.mail"
              label="Województwo"
              outlined
              readonly
            ></v-text-field>
        </v-col>
                <v-col cols="12" sm="6" md="6">
            <v-text-field
              :value="processData.resupplyRequest.purchaserData.phone"
              label="Powiat"
              outlined
              readonly
            ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="6">
            <v-text-field
              :value="processData.resupplyRequest.purchaserData.id"
              label="Nazwa Magazynu"
              outlined
              readonly
            ></v-text-field>
        </v-col>
        </v-row>
        </v-container>
        <v-container>
            <v-card-actions >
            <v-btn block x-large color="success" @click="save"> Wyślij  </v-btn>
            </v-card-actions>
        </v-container>
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