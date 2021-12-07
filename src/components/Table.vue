<template>
  <table>
    <TableItem
      v-for="row in rows"
      v-bind:key="row.title"
      :row="row"
      />
  </table>
</template>

<script>
import TableItem from "./TableItem.vue"
export default {
  props: ["rows"],
  components: {TableItem},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
