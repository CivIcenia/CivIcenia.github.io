<template>
  <v-navigation-drawer
      v-model="drawer"
      permanent
      expand-on-hover
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          routerf
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
</template>

<script>
export default {
    data() { 
        return {
            drawer: true,
            items: [
              {
                icon: 'mdi-home',
                title: 'Home',
                to: '/'
              },
        {
          icon: 'mdi-file-document-multiple',
          title: 'Constitution',
          to: '/gov/constitution',
        }
      ],
        }
    }
}
</script>

<style>

</style>