<template>
  <div id="app">
    <v-app>
      <app-header> </app-header>
      <v-content>
        <router-view />
      </v-content>
    </v-app>
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader";

export default {
  components: {
    AppHeader
  }
};

//   data: () => ({
//     //
//   })
// };
</script>
