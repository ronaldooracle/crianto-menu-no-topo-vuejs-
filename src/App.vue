<template>
  <v-app>
    <v-app-bar app color="secundary" dark>
      <div class="text-center">
        <v-menu offset-y>
          <template v-slot:activator="{ on, attrs }">
            <v-btn color="secundary" dark v-bind="attrs" v-on="on">
              Bem Vindo
            </v-btn>
          </template>
          <v-list>
            <v-list-item
              v-for="(item, i) in items"
              :key="i"
              link
              :to="{ path: item.path }"
            >
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
        <v-menu offset-y>
          <template v-slot:activator="{ on, attrs }">
            <v-btn
              color="secundary"
              dark
              v-bind="attrs"
              v-on="on"
              to="/contact"
            >
              Contato
            </v-btn>
            <v-btn color="secundary" dark v-bind="attrs" v-on="on" to="/about">
              Sobre
            </v-btn>
            <v-btn color="secundary" dark v-bind="attrs" v-on="on" to="/perfil">
              Perfil
            </v-btn>
          </template>
        </v-menu>
      </div>
      <v-spacer></v-spacer>
      <div class="d-flex align-center">
        <v-avatar>
          <img
            src="https://avatars.githubusercontent.com/u/30814275?v=4"
            alt="John"
          />
        </v-avatar>
      </div>
    </v-app-bar>
    <Carousel />

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>
<script>
import Carousel from "./components/Carousel.vue";
export default {
  components: {
    Carousel,
  },
  data: () => ({
    items: [
      {
        title: "Home",
        path: "/",
      },
      {
        title: "Sobre",
        path: "/about",
      },
      {
        title: "Contato",
        path: "/contact",
      },
      {
        title: "Perfil",
        path: "/perfil",
      },
    ],
  }),
};
</script>

<style>
li {
  display: inline;
  font-family: "Times New Roman", Times, serif;
  text-decoration: none;
  font-size: 15px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
