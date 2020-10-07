<template>
  <div class="card" style="width: 18rem">
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
    const increase = () => {
      //this.$emit('subtract-from-wallet', props.price )
      quantity.value++;
    };
    const decrease = () => {
      if (quantity.value > 0) {
        //this.$emit('add-to-wallet', props.price )
        quantity.value--;
      }
    };
    return {
      quantity,
      increase,
      decrease,
      displayPrice: props.price ? props.price.toFixed(2) : "0.00",
      ratingValue,
    };
  },
};
</script>

<style>
.card {
  width: 100% !important;
}
</style>