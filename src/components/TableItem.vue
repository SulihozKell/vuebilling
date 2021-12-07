<template>
    <tr>
        <th>{{title}}</th>
        <td>{{price}}</td>
        <td>{{quantity}}</td>
    </tr>
</template>

<script>
export default {
    props: ["row"],
    data() {
        return {
            title: this.row.title,
            price: this.row.price,
            quantity: this.row.quantity,
        }
    }
}
</script>
