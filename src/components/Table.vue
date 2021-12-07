<template>
  <table>
    <TableItem
      v-for="row in rows"
      v-bind:key="row.title"
      :row="row"
      @selected-row-changed="Changed"
    />
  </table>
</template>

<script>
import TableItem from "./TableItem.vue"
export default {
  props: ["rows"],
  components: {TableItem},
  methods: {
    Changed(e) {
      TableItem.$emit("selected-title-changed", e)
      TableItem.$emit("selected-price-changed", e)
      TableItem.$emit("selected-quantity-changed", e)
    }
  }
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
