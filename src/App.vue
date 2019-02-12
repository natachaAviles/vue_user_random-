<template id="app">
  <v-app id="keep">
    <!-- drawer-->
    <v-navigation-drawer v-model="drawer" class="drawer" fixed clipped app>
      <v-list dense class="white">
        <template></template>
      </v-list>
    </v-navigation-drawer>

    <!-- toolbar -->
    <v-toolbar color="amber" app absolute clipped-left>
      <v-toolbar-side-icon @click="drawer = !drawer"></v-toolbar-side-icon>
      <span class="title ml-3 mr-5">
        Google&nbsp;
        <span class="font-weight-light">Keep</span>
      </span>
      <v-text-field solo-inverted flat hide-details label="Search" prepend-inner-icon="search"></v-text-field>
      <v-spacer></v-spacer>
    </v-toolbar>
    <v-content>
      <v-container fluid fill-height class="grey lighten-4">
        <v-layout justify-center align-center>
          <HelloWorld></HelloWorld>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  components: {
    HelloWorld
  },
  data: () => ({
    drawer: null
  }),
  props: {
    source: String
  }
};
</script>

<style >
#keep .v-navigation-drawer__border {
  display: none;
}
</style>





<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.drawer {
  background-image: url("https://images.pexels.com/photos/4827/nature-forest-trees-fog.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940");
  background-size: cover;
}
</style>
