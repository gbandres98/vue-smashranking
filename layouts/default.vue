<template>
  <v-app>
    <v-app-bar fixed app>
      <v-toolbar-title class="title" v-text="'Smash Ranking Cutre'" />
      <v-toolbar-items>
        <v-btn to="/" flat>
          <v-icon dense class="menu__icon">fas fa-home</v-icon>
          <span class="hidden-xs-only">Home</span>
        </v-btn>
        <v-btn to="rankings" flat>
          <v-icon dense class="menu__icon">fas fa-list-ol</v-icon>
          <span class="hidden-xs-only">Rankings</span>
        </v-btn>
        <v-btn to="sets" flat>
          <v-icon dense class="menu__icon">fas fa-gamepad</v-icon>
          <span class="hidden-xs-only">Sets</span>
        </v-btn>
      </v-toolbar-items>
      <v-spacer />
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer fixed app>
      <span
        >&copy; {{ new Date().getFullYear() }} Marah &
        <a href="https://github.com/gbandres98">gbandres</a></span
      >
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      appTitle: "Awesome App",
      sidebar: false,
      menuItems: [
        { title: "Home", path: "/home", icon: "home" },
        { title: "Sign Up", path: "/signup", icon: "face" },
        { title: "Sign In", path: "/signin", icon: "lock_open" }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.title {
  margin-right: 50px;
}

.menu__icon {
  margin-right: 10px;
}
</style>
