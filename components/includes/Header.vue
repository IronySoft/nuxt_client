<template>
  <v-toolbar
    :clipped-left="clipped"
    fixed
    app
  >
    <v-toolbar-side-icon @click="drawer = !drawer" />
    <v-btn
      icon
      @click.stop="miniVariant = !miniVariant"
    >
      <v-icon>{{ `chevron_${miniVariant ? 'right' : 'left'}` }}</v-icon>
    </v-btn>
    <v-btn
      icon
      @click.stop="clipped = !clipped"
    >
      <v-icon>web</v-icon>
    </v-btn>
    <v-btn
      icon
      @click.stop="fixed = !fixed"
    >
      <v-icon>remove</v-icon>
    </v-btn>
    <v-toolbar-title v-text="title" />
    <v-spacer />
    <v-btn
      icon
      @click.stop="rightDrawer = !rightDrawer"
    >
      <v-icon>menu</v-icon>
    </v-btn>
  </v-toolbar>
</template>

<script>
    export default {
        name: "Header",
      data() {
        return {
          clipped: false,
          drawer: false,
          fixed: false,
          miniVariant: false,
          right: true,
          rightDrawer: false,
          title: 'Vuetify.js'
        }
      }
    }
</script>

<style scoped>

</style>
