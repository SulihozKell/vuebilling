<template>
  <table>
    <tr>
      <th>Név</th>
      <th>Ár</th>
      <th>Darabszám</th>
      <th>Összértékét</th>
      <th>Operations</th>
    </tr>
    <TableItem
      v-for="row in rows"
      v-bind:key="row.title"
      :row="row"
      @selected-row-changed="Changed"
      @row-item-deleted="Deleted"
      @new-row-created="New"
    />
    <tr>
      <td><input type="text"></td>
      <td><input type="text"></td>
      <td><input type="text"></td>
      <td><button @click="New">New</button></td>
    </tr>
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
    },
    Deleted(e) {
      this.$emit("row-item-deleted", e)
    },
    New() {
      this.$emit('new-row-created', {
        title: this.title,
        price: this.price,
        quantity: this.quantity
      })
    }
  }
}
</script>
