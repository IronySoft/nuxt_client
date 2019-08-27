<template>
  <v-footer
    :fixed="fixed"
    app
  >
    <span>&copy; 2019</span>
  </v-footer>
</template>

<script>
    export default {
        name: "Footer",
      data(){
          return{
            fixed: true
          }
      }
    }
</script>

<style scoped>

</style>
