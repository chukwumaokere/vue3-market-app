<template>
  <button :class="className">{{ text }}</button>
</template>

<script>
export default {
  props: {
    text: String,
    className: String,
  },
};
</script>

<style>
</style>