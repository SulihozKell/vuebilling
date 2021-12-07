<template>
    <div>
        <tr>
            <td>{{title}}</td>
            <td>{{price}}</td>
            <td>{{quantity}}</td>
            <td>{{quantity * price}}</td>
            <td v-if="edit">Operations</td>
            <td v-if="!edit"><button @click="Edit">Edit</button></td>
        </tr>
        <tr v-if="edit">
            <td><input type="text" v-model="title"></td>
            <td><input type="text" v-model="price"></td>
            <td><input type="text" v-model="quantity"></td>
            <td>
                <button @click="Delete(row)">X</button>
                <button @click="Save">Save</button>
            </td>
        </tr>
    </div>
</template>

<script>
export default {
    props: ["row"],
    data() {
        return {
            title: this.row.title,
            price: this.row.price,
            quantity: this.row.quantity,
            edit: false
        }
    },
    methods: {
        Edit() {
            this.edit = true
        },
        Save() {
            this.edit = false
            this.$emit("selected-title-changed", {
                original: this.row,
                new: {
                    title: this.title
                },
            }),
            this.$emit("selected-price-changed", {
                original: this.row,
                new: {
                    price: this.price
                },
            }),
            this.$emit("selected-quantity-changed", {
                original: this.row,
                new: {
                    quantity: this.quantity
                },
            })
        },
        Delete(index) {
            this.edit = false
            //this.rows.splice(this, 1);
            /*this.$emit("row-item-deleted", {
                original: this.row,
                new : {
                    title: null,
                    price: null,
                    quantity: null
                },
            })*/
            this.$delete(this, index)
        }
    }
}
</script>
