<template>
  <v-app>
    <div>
      <v-container>
        <v-row class="top">
          <v-col>
            <v-img
              class="logo"
              :src="mypage"
              max-width="100px"
              max-height="100px"
            ></v-img>
          </v-col>

          <v-spacer></v-spacer>
          <v-col v-for="n in pages" :key="n">
            <v-card outlined tile>
              <router-link :to="n.link">{{ n.name }}</router-link>
            </v-card>
          </v-col>
        </v-row>

        <router-view></router-view>
      </v-container>
    </div>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    pages: [
      { name: "Home", link: "/" },
      { name: "Msg", link: "/v" },
      { name: "Photo", link: "/s" },
      { name: "Intern", link: "/c" },
    ],
    mypage: require("./assets/mypage.png"),
    logo: require("./assets/Insta_logo.png"),
    items: [{ title: "ome" }, { title: "about" }],
  }),
};
</script>
<style>
.top {
  padding: 50px;
}
</style>
