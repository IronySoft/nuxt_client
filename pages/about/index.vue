<template>

<div>
  <nuxt-link to="/about/1">
    <Card :card_text="card_text" :imageUrl="imageUrl"></Card>
  </nuxt-link>
</div>
</template>

<script>
  import Card from '../../components/About'

  export default {
    name: "index",
    layout:'aboutLayout',
    data() {
      return {
        card_text: 'Lorem ipsum dolor sit amet, brute iriure accusata ne mea. Eos suavitate referrentur ad, te duo agam libris qualisque, utroque quaestio accommodare no qui. Et percipit laboramus usu, no invidunt verterem nominati mel. Dolorem ancillae an mei, ut putant invenire splendide mel, ea nec propriae adipisci. Ignota salutandi accusamus in sed, et per malis fuisset, qui id ludus appareat.'
        ,
        imageUrl: 'https://cdn.vuetifyjs.com/images/cards/desert.jpg'
      }
    },
    components: {
      Card
    },
    head() {
      return {
        title: 'Contact',
        meta: [
          {hid: 'description2', name: 'description', content: 'description'}
        ]
      }
    }
  }
</script>

<style scoped>

</style>

