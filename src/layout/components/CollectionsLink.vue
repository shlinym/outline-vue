<template>
  <v-list dense>
    <template v-for="(node, i) in nodes">
      <!-- <v-list-group
        sub-group
        :key="i"
        v-if="node.children && node.children.length"
      >
        <template v-slot:activator>
          <v-list-item-content>
            <v-list-item-title v-text="node.text"></v-list-item-title>
          </v-list-item-content>
          <v-list-item-action class="pa-0 ma-0">
            <v-btn x-small icon>
              <v-icon>mdi-dots-horizontal</v-icon>
            </v-btn>
          </v-list-item-action>
        </template>
        <collections-link class="py-0 pl-3" :nodes="node.children" />
      </v-list-group> -->

      <v-list-item :key="i">
        <!-- <div>{{ node.text }}</div> -->

        <v-list-item-content>
          <v-list-item-title v-text="node.text"></v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <v-list-item :key="i">
        <v-list-item-icon>
          <v-icon>mdi-home</v-icon>
        </v-list-item-icon>

        <v-list-item-title>Home</v-list-item-title>
      </v-list-item>

      <!-- <v-list-item :key="i">
        <v-list-item-content>
          <v-list-item-title v-text="node.text"></v-list-item-title>
        </v-list-item-content>
      </v-list-item> -->
    </template>
  </v-list>
</template>

<script>
export default {
  name: "collections-link",
  props: ["nodes", "text", "children"],
  created() {
    this.$log.debug(this.nodes);
    this.$log.debug(this.nodes[0].text);
  },
  data() {
    return {
      listIndex: 0
    };
  }
};
</script>
