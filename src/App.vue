<template>
  <div id="app">
    <Table :rows="rows" />
  </div>
</template>

<script>
import Table from "./components/Table.vue"
export default {
  name: 'App',
  components: {Table},
  data() {
    return {
      rows: [
        {
          title: 'Kerék',
          price: 100,
          quantity: 12
        },
        {
          title: 'Teleszkóp',
          price: 1000,
          quantity: 300
        },
        {
          title: 'Kormány',
          price: 230,
          quantity: 5
        },
        {
          title: 'Ajtó',
          price: 45120,
          quantity: 321
        },
      ]
    }
  }
}
</script>
