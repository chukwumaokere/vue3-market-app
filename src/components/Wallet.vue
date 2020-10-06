<template>
  <button class="btn btn-primary">Wallet: {{ amountDisplay }}</button>
</template>

<script>
let amount = 50;
let amountDisplay = "$" + amount.toFixed(2);
export default {
  setup() {
    return {
      amountDisplay,
      amount,
    };
  },
};
</script>

<style>
</style>