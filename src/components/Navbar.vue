<template>
  <nav class="navbar sticky-top navbar-expand-lg navbar-dark bg-dark">
    <Container>
      <button
        class="navbar-toggler float-left"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <a class="navbar-brand" href="#"><Logo /> &nbsp; Chucks's Store</a>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <a class="nav-link" href="#">Home</a>
          </li>
          <li class="nav-item active">
            <a class="nav-link" href="#">Menu</a>
          </li>
        </ul>
      </div>
      <div class="float-right">
        <Button text="Checkout" className="btn btn-danger" />
        &nbsp;
        <!-- JUST TESTING REF VALUE <p> {{ amt }} </p> -->
        <Wallet :amount="amt" />
      </div>
    </Container>
  </nav>
</template>

<script>
import Logo from "./Logo";
import Button from "./Button";
import Container from "./Container";
import Wallet from "./Wallet";
export default {
  props: {
    amt: Number,
  },
  components: {
    Logo,
    Button,
    Container,
    Wallet,
  },
};
</script>

<style>
</style>