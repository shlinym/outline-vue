<template>
  <v-container>
    <v-list dense>
      <v-list-item-group color="primary">
        <sidebar-link
          v-for="(item, i) in items"
          :key="i"
          :icon="item.icon"
          :text="item.text"
        ></sidebar-link>
      </v-list-item-group>
    </v-list>
  </v-container>
</template>

<script>
import SidebarLink from "../components/SidebarLink";

export default {
  components: {
    SidebarLink
  },
  data: () => ({
    item: 1,
    items: [
      { text: "Home", icon: "mdi-home" },
      { text: "Search", icon: "mdi-file-search" }
    ]
  })
};
</script>
