<template>
  <v-app>
    <v-app-bar
      color="gray"
      dense
    >
      <v-tabs align-with-title>
        <v-tab>Home</v-tab>
        <v-tab>About Us</v-tab>
        <v-tab>Email</v-tab>
      </v-tabs>
    </v-app-bar>
    <div class="d-flex text-center flex-column flex-md-row flex-grow-1">
      <div
        class="pa-2 pa-md-4 flex-grow-1 align-center justify-center d-flex flex-column"
      >
        <div class="layout-content ma-auto w-full">
          <nuxt />
        </div>
        <div class="caption mt-4">

        </div>
      </div>
    </div>
    <notifications position="top center" />

    <v-footer padless>
        <v-img
          src="https://treehousecreativeco.com/wp-content/uploads/2019/04/footer-skyline-background.jpg"
          max-height="40"
          max-width="1550"
        ></v-img>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "auth"
}
</script>

<style scoped>

</style>
