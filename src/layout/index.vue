<template>
  <v-app id="inspire" flex>
    <side-bar ref="side" />

    <v-content ref="app">
      <v-container class="fill-height" fluid align-start>
        <app-main height="100%" width="100%" />
      </v-container>
    </v-content>

    <dialog-button />
  </v-app>
</template>

<script>
import AppMain from "./components/AppMain";
import SideBar from "./components/SideBar";
import DialogButton from "./components/DialogButton";

// import { bus } from "@/utils/bus";

export default {
  name: "Layout",
  components: {
    AppMain,
    SideBar,
    DialogButton
  },
  props: {
    source: String
  },
  data() {
    return {
      sideWidth: null
      // appWidth: "calc(100vh-256px)"
    };
  },
  computed: {
    // sideWidth() {
    //   return this.sideWidth;
    // }
  },
  watch: {
    sideWidth: function(newVal, oldVal) {
      this.$nextTick(() => {
        console.log(newVal, oldVal);
      });
    }
  },
  created() {
    // bus.$on("nav-width-change", this.updateAppWidth);
  },
  mounted() {
    this.sideWidth = this.$refs.side.$el.style.width;
    console.log(this.sideWidth);
  },
  beforeDestroy() {
    // bus.$off("nav-width-change", this.updateAppWidth);
  },
  methods: {
    updateAppWidth(width) {
      this.appWidth = "calc(100vh-" + width + ")";
      console.log(width);
      console.log(this.appWidth);
    }
  }
};
</script>
