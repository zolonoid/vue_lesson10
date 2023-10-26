<template>
    <div class="product-details">
        <div class="product-details__name">
            {{ productName }}
        </div>
        <div class="product-details__price">
            {{ formattedPrice }}
        </div>
        <div class="product-details__available" :class="{ 'product-details__available_yes': available }">
            {{ availableText }}
        </div>
    </div>
</template>

<script>
export default {
    props: {
        productName: String,
        price: Number,
        available: Boolean
    },
    computed: {
        formattedPrice() {
            return '$' + this.price.toPrecision(4);
        },
        availableText() {
            return this.available ? "Available" : "Out of stock";
        }
    },
}
</script>

<style lang="scss">
.product-details {
    width: 100%;
    border: 2px solid gray;
    background-color:darkgray;
    padding-top: 30px;
    padding-bottom: 30px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 40px;

    &__name {
        font-size: large;
    }

    &__price {
        font-size: larger;
        color: gold;
    }

    &__available {
        font-size: medium;
        color: red;

        &_yes {
            color: green;
        }
    }
}
</style>