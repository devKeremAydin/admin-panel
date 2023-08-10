<template>
  <v-navigation-drawer v-model="localDrawer" app style="background-color: #131313;">

    <v-img src="">
      <div class="text-center">
        <v-avatar class="mt-4" color="grey darken-1" size="64">
          <v-img src="https://avatars.githubusercontent.com/u/64500329?v=4"></v-img>
        </v-avatar>
        <h3 style="color: white;">krmydn7@gmail.com</h3>
      </div>
      
    </v-img>

    <v-divider></v-divider>

    <v-list>
      <v-list-item v-for="[icon, text] in links" :key="icon" link>
        <v-list-item-icon>
          <v-icon style="color: white;">{{ icon }}</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title style="color: white;">{{ text }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  name: "SideBar",
  props: ["drawer"],
  data() {
    return {
      localDrawer:this.drawer,
      links: [
        ["mdi-microsoft-windows", "Dashboard"],
        ["mdi-account", "Profile"],
        ["mdi-clipboard-list-outline", "Products"],
        ["mdi-card-account-details-outline", "Orders"],
        ["mdi-cog", "System Setting"],
      ],
    };
  },
  watch: {
    drawer(newVal) {
      this.localDrawer = newVal;
    },
    localDrawer(newVal) {
      this.$emit("update:drawer", newVal);
    },
  },
};
</script>

<style></style>
