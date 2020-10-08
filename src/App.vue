<template>
  <Navbar :amt="walletAmount" />
  <Container class="chucks-grid">
    <Card
      v-for="food in foods"
      :key="food._id"
      :price="food.price"
      :productName="food.product"
      :manufacturer="food.manufacturer"
      :rating="food.rating"
      @update-wallet="updateWallet"
    />
  </Container>
</template>

<script>
import Navbar from "./components/Navbar";
import Card from "./components/Card";
import Container from "./components/Container";
import * as foods from "./assets/foods.json";
import { ref } from "vue";
//Starting value of wallet
export default {
  name: "App",
  components: {
    Navbar,
    Card,
    Container,
  },
  setup() {
    const walletAmount = ref(50);
    return {
      foods,
      walletAmount,
    };
  },
  methods: {
    updateWallet(val) {
      //console.log("event called", this.walletAmount, val);
      this.walletAmount = this.walletAmount + val;
      //console.log(this.walletAmount);
    },
  },
};
</script>

<style>
.chucks-grid {
  margin-top: 3rem;
  display: grid;
  margin-bottom: 3rem;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  column-gap: 1rem;
  row-gap: 1rem;
}
</style>
