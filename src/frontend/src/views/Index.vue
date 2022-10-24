<template>
  <header class="header">
    <div class="header__logo">
      <a href="index.html" class="logo">
        <img src="@/assets/img/logo.svg" alt="V!U!E! Pizza logo" />
      </a>
    </div>
    <div class="header__cart">
      <a href="cart.html">0 ₽</a>
    </div>
    <div class="header__user">
      <a href="#">
        <span class="layout__link">Войти</span>
      </a>
    </div>
  </header>
</template>

<script>
import user from "@/static/user.json";
import pizza from "@/static/pizza.json";
import misc from "@/static/misc.json";
export default {
  name: "Index",
  data() {
    return {
      user,
      pizza,
      misc,
    };
  },
};
</script>

<style lang="scss">
@import "~@/assets/scss/app";
</style>
