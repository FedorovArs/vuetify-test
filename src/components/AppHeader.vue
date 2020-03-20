<template>
  <div>
    <v-navigation-drawer absolute temporary v-model="drawer" app :width="400">
      <v-list dense>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-folder-multiple</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Внутренние отправления</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-folder-multiple</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Международные отправления</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-toolbar dark class="primary">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="projectTitle"></v-toolbar-title>
    </v-toolbar>
  </div>
</template>

<script>
export default {
  data: () => ({
    projectTitle: "Управление контрольными сроками",
    drawer: false
  })
};
</script>

<style scoped></style>
