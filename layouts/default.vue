<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn
        icon
        @click.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light>
              mdi-repeat
            </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-footer>
      <v-img
        src="https://treehousecreativeco.com/wp-content/uploads/2019/04/footer-skyline-background.jpg"
        max-height="80"
        max-width="1550"
      ></v-img>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-folder-account',
          title: 'Staff',
          to: '/staffs/list'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Borrow',
          to: '/borrows/list'
        },
        {
          icon: 'mdi-collage',
          title: 'Product',
          to: '/products/list'
        },
        {
          icon: 'mdi-clipboard-account',
          title: 'Admin Info',
          to: '/admins/list'
        },
        {
          icon: 'mdi-account',
          title: 'User Info',
          to: '/users/list'
        },
        {
          icon: 'mdi-settings',
          title: 'Setting',
          to: '/setting'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Web Development'
    }
  }
}
</script>
