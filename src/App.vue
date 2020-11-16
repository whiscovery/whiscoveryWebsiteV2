<template>
  <v-app id="inspire">
    <v-app-bar dense app color="white" flat>
      <v-avatar
        :color="$vuetify.breakpoint.smAndDown ? 'grey darken-1' : 'transparent'"
        size="32"
      ></v-avatar>

      <v-tabs centered class="ml-n9" color="grey darken-1">
        <v-tab v-for="link in links" :key="link">
          {{ link }}
        </v-tab>
      </v-tabs>

      <v-avatar
        class="hidden-sm-and-down"
        color="grey darken-1 shrink"
        size="32"
      ></v-avatar>
    </v-app-bar>
    <v-main>
      <v-container class="tester">
        <v-row>
          <v-col vols="12"
            ><div class="top">
              whiscovery
            </div></v-col
          >
        </v-row>
        <v-row class="tester">
          <v-col cols="12" sm="9">
            <router-view></router-view>
          </v-col>

          <v-col cols="12" sm="3">
            <RightmenuComponent></RightmenuComponent>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import RightmenuComponent from "./components/Rightmenu";
export default {
  name: "App",
  components: {
    RightmenuComponent
  },
  data: () => ({
    //
  })
};
</script>
<style>
.top {
  background: rgb(208, 255, 0);
  background: -webkit-linear-gradient(left, #d3ff8b, rgb(216, 255, 125));
  background: -moz-linear-gradient(right, #d3ff8b, rgb(255, 97, 97));
  background: -o-linear-gradient(right, #d3ff8b, rgb(255, 117, 117));
  background: linear-gradient(to right, rgb(136, 255, 0), rgb(234, 255, 196));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  font-family: "Lobster", cursive;
  font-size: 100px;
  text-align: center;
  margin: 0px 0px 0px 5px;
  padding: 0px;
  width: 100%;
  z-index: 1;
}
.div-menu {
  width: 100%;
  text-align: center;
  margin: 20px 0px 0 0px;
}
.tester {
  display: inline;
  width: 100%;
  padding: 0;
  margin: 0;
}
</style>
