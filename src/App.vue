<template>
  <v-app>
    <v-btn color="green" dark @click="sheet = !sheet">
      Add feedback
    </v-btn>
    <dashboard />
    <glisten-client
      :sheet="sheet"
      :application-id="applicationID"
      :user-name="userName"
      :custom-tracker="customTracker"
      @close="toggleFeedback"
    />
    <glisten-csat :filtered-applications="['iadc-portal']" />
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';
import { Component } from 'vue-property-decorator';
import Dashboard from './components/GlistenDashboard.vue';
import GlistenClient from './components/GlistenClient.vue';
import GlistenCsat from '@/components/GlistenCsat.vue';
import {
  VApp,
  VDataTable,
  VIcon,
  VSnackbar,
  VTooltip,
  VListItem,
  VListItemContent,
  VListItemTitle,
  VListItemSubtitle,
  VMenu,
  VTextarea,
  VCheckbox,
  VChip,
  VBtn,
  VDatePicker,
  VBottomSheet,
  VSheet,
  VRating,
  VSelect,
  VRow,
  VCol,
  VContainer,
  VSwitch,
  VTextField,
  VCard,
} from 'vuetify/lib';

/**
 * App component entry default
 */
@Component({
  components: {
    Dashboard,
    GlistenClient,
    GlistenCsat,
    VApp,
    VDataTable,
    VIcon,
    VSnackbar,
    VTooltip,
    VListItem,
    VListItemContent,
    VListItemTitle,
    VListItemSubtitle,
    VMenu,
    VTextarea,
    VCheckbox,
    VChip,
    VBtn,
    VDatePicker,
    VBottomSheet,
    VSheet,
    VRating,
    VSelect,
    VRow,
    VCol,
    VContainer,
    VSwitch,
    VTextField,
    VCard,
  },
})
export default class App extends Vue {
  public applicationID = 'GLISTEN';
  public userName = 'User';

  public customTracker = {
    contextPortal: window.location.href,
    contextPage: '',
  };

  public sheet = false;

  private toggleFeedback(event: any) {
    this.sheet = false;
  }
}
</script>
