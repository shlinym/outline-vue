<template>
  <v-hover v-slot:default="{ hover }" close-delay="200">
    <v-list-item :key="key">
      <v-list-item-icon>
        <v-icon v-text="icon"></v-icon>
      </v-list-item-icon>
      <v-list-item-content>
        <v-list-item-title v-text="text"></v-list-item-title>
      </v-list-item-content>

      <!-- <v-list-item-action pa-0>
        <v-btn x-small icon>
          <v-icon>mdi-dots-horizontal</v-icon>
        </v-btn>
      </v-list-item-action>-->

      <v-list-item-action class="pa-0 ma-0">
        <v-btn x-small icon v-if="hover">
          <v-icon>mdi-dots-horizontal</v-icon>
        </v-btn>
      </v-list-item-action>
    </v-list-item>
  </v-hover>
</template>

<script>
export default {
  props: ["key", "icon", "text", "menu"]
};
</script>
