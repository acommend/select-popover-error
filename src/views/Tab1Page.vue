<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Select Error for Interface Popover</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-select label="Select" v-model="selectedValueRef" interface="popover">
        <ion-select-option
          v-for="(value, index) in values"
          :key="index"
          :value="value"
          >{{ value }}</ion-select-option
        >
      </ion-select>
      <ion-input label="Selected value" v-model="selectedValueRef" readonly />
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonSelect,
  IonSelectOption,
  IonInput,
} from "@ionic/vue";

export default defineComponent({
  name: "Tab1Page",
  components: {
    IonPage,
    IonHeader,
    IonToolbar,
    IonTitle,
    IonContent,
    IonSelect,
    IonSelectOption,
    IonInput,
  },
  setup() {
    const values = ["Foo", "Bar"];
    const selectedValueRef = ref(values[0]);
    return {
      values,
      selectedValueRef,
    };
  },
});
</script>
