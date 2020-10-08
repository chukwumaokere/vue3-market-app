<template>
  <button class="btn btn-primary">Wallet: ${{ amount.toFixed(2) }}</button>
</template>

<script>
export default {
  props: {
    amount: Number,
  },
};
</script>

<style>
</style>