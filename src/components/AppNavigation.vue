<template>
  <span>
    <v-navigation-drawer
      app
      v-model="drawer"
      class="brown lighten-2"
      dark
      disable-resize-watcher
    >
      <v-list>
        <template v-for="(item, index) in items">
          <v-list-item-content :key="index">
            <v-list-item-title>
              {{ item.title }}
            </v-list-item-title>
          </v-list-item-content>
          <v-divider :key="`divider-${index}`"></v-divider>
        </template>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar dense color="indigo darken-2" dark app>
      <v-app-bar-nav-icon
        class="hidden-md-and-up"
        @click="drawer = !drawer"
      ></v-app-bar-nav-icon>
      <!-- <v-spacer class="hidden-md-and-up"></v-spacer> -->
      <v-toolbar-title>{{ appTitle }}</v-toolbar-title>
      <v-btn class="hidden-sm-and-down">Menu</v-btn>
      <v-spacer class="hidden-sm-and-down"></v-spacer>
      <v-btn class="hidden-sm-and-down">SIGN IN</v-btn>
      <v-btn color="brown lighten-3" class="hidden-sm-and-down">JOIN</v-btn>
    </v-app-bar>
  </span>
</template>
<script>
export default {
  name: 'AppNavigation',
  data() {
    return {
      appTitle: 'Meal Prep',
      drawer: false,
      items: [{ title: 'Menu' }, { title: 'Sign In' }, { title: 'Join' }]
    };
  }
};
</script>
