<template>
  <v-app id="inspire">
    <v-card-title>
      <v-toolbar dark class="elevation-2" color="cyan">
        <v-toolbar-title>aims-vuetify-money</v-toolbar-title>
      </v-toolbar>
    </v-card-title>
    <v-card-text>
      <v-container>
        <v-row>
          <v-col cols="4" sm="4" md="4">
            <aims-vuetify-money
              v-model="value1"
              v-bind:label="label1"
              v-bind:readonly="readonly1"
              v-bind:disabled="disabled1"
              v-bind:outlined="outlined1"
              v-bind:clearable="clearable1"
              v-bind:valueWhenIsEmpty="valueWhenIsEmpty1"
              v-bind:options="options1"
              v-bind:properties="properties1"
              :valueOptions="valueOptions1"
              v-on:CustomMinEvent="value1 = $event"
              v-on:CustomMaxEvent="value1 = $event"
            />
            Parent v-model: {{ value1 }}
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="4" sm="4" md="4">
            <aims-vuetify-money
              v-model="value2"
              v-bind:label="label2"
              v-bind:readonly="readonly2"
              v-bind:disabled="disabled2"
              v-bind:outlined="outlined2"
              v-bind:clearable="clearable2"
              v-bind:valueWhenIsEmpty="valueWhenIsEmpty2"
              v-bind:options="options2"
              v-bind:properties="properties2"
            />
            Parent v-model: {{ value2 }}
          </v-col>
        </v-row>
      </v-container>
    </v-card-text>
  </v-app>
</template>

<script>
import VuetifyMoney from "./components/VuetifyMoney.vue";

export default {
  name: "app",
  components: {
    "aims-vuetify-money": VuetifyMoney
  },
  data: () => ({
    value1: "1250.03",
    label1: "Valor pt-BR",
    readonly1: false,
    disabled1: false,
    outlined1: true,
    clearable1: true,
    valueWhenIsEmpty1: "", // "0" or "" or null
    valueOptions1: {
      min: 1000,
      minEvent: "CustomMinEvent",
      max: 10000,
      maxEvent: "CustomMaxEvent"
    },
    options1: {
      locale: "pt-BR",
      prefix: "R$",
      suffix: "",
      length: 11,
      precision: 2
    },
    properties1: {
      hint: "my hint 1"
    },

    value2: "1250.03",
    label2: "Value en-US",
    readonly2: false,
    disabled2: false,
    outlined2: true,
    clearable2: true,
    valueWhenIsEmpty2: "", // "0" or "" or null
    options2: {
      locale: "en-US",
      prefix: "U$",
      suffix: "",
      length: 7,
      precision: 2
    },
    properties2: {
      hint: "my hint 2"
    }
  })
};
</script>
