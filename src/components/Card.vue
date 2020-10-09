<template>
  <div class="card" :class="{ cardpicked: quantity > 0 }" style="width: 18rem">
    <img
      class="card-img-top"
      src="https://www.flaticon.com/svg/static/icons/svg/1377/1377194.svg"
      alt="Card image cap"
    />
    <div class="card-body">
      <h5 class="card-title">{{ productName }}</h5>
      <p class="card-text">
        Manufacturer: {{ manufacturer }} <br />
        Rating: {{ ratingValue }} <br />
        Price: <b> ${{ displayPrice }} </b>
      </p>
      <div class="btn-group" role="group" aria-label="Basic example">
        <button type="button" class="btn btn-secondary" @click="decrease()">
          -
        </button>
        <button type="button" class="btn btn-secondary" disabled>
          {{ quantity }}
        </button>
        <button type="button" class="btn btn-secondary" @click="increase()">
          +
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  props: {
    productName: String,
    manufacturer: String,
    rating: Number,
    price: Number,
  },

  setup(props) {
    let ratingValue = props.rating ? props.rating : "N/A";
    let quantity = ref("");
    quantity.value = 0;
    return {
      quantity,
      displayPrice: props.price ? props.price.toFixed(2) : "0.00",
      ratingValue,
    };
  },
  methods: {
    increase() {
      this.quantity++;
      this.$emit("update-wallet", -Math.abs(this.$props.price));
    },
    decrease() {
      if (this.quantity > 0) {
        this.$emit("update-wallet", this.$props.price);
        this.quantity--;
      }
    },
  },
};
</script>

<style>
.card {
  width: 100% !important;
}

.cardpicked {
  border-color: green;
  border-width: thick;
}
</style>