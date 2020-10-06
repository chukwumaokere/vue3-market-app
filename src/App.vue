<template>
  <Navbar />
  <Container class="chucks-grid">
    <Card
      v-for="food in foods"
      :key="food._id"
      :price="food.price"
      :productName="food.product"
      :manufacturer="food.manufacturer"
      :rating="food.rating"
    />
  </Container>
</template>

<script>
import Navbar from "./components/Navbar";
import Card from "./components/Card";
import Container from "./components/Container";
import * as foods from "./assets/foods.json";
export default {
  name: "App",
  components: {
    Navbar,
    Card,
    Container,
  },
  setup() {
    return {
      foods,
    };
  },
};
</script>

<style>
.chucks-grid {
  margin-top: 3rem;
  display: grid;
  grid-template-columns: auto auto auto auto;
  column-gap: 1rem;
  row-gap: 1rem;
}
</style>
