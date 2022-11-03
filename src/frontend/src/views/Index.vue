<template>
  <div>
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
    <content class="content">
      <div class="content__wrapper">
        <h class="title title--big">Конструктор пиццы</h>
      </div>
      <div class="content__diameter">
        <h class="title title--small sheet__title">Выберите размер</h>
        <div class="sheet__content diameter">
          <label
            v-for="{ id, name, value } in sizes"
            :class="`diameter__input diameter__input--${value}`"
            :key="id"
          >
            <span>{{ name }}</span>
          </label>
        </div>
      </div>
      <div class="content__dough">
        <h class="title title--small sheet__title">Выберите тесто</h>
        <div class="sheet__content doughs">
          <label
            v-for="{ id, name, value } in doughs"
            :class="`dough__input dough__input--${value}`"
            :key="id"
          >
            <span>{{ name }}</span>
          </label>
        </div>
      </div>
      <div class="content__ingredients">
        <h class="title title--small sheet__title">Выберите ингридиенты</h>
        <div class="sheet__content ingredients">
          <label
            v-for="{ id, name, value } in ingredients"
            :class="`ingredients__input ingredients__input--${value}`"
            :key="id"
          >
            <span>{{ name }}</span>
          </label>
        </div>
      </div>
      <div>
        <h class="title title--small sheet__title">Выберите соус</h>
        <div class="sheet__content sauces">
          <label
            v-for="{ id, name, value } in sauces"
            :class="`ingredients__sauce ingredients__sauce--${value}`"
            :key="id"
          >
            <span>{{ name }}</span>
          </label>
        </div>
      </div>
    </content>
  </div>
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
  computed: {
    doughs() {
      return this.pizza.dough.map((dough) => ({
        ...dough,
      }));
    },
    ingredients() {
      return this.pizza.ingredients.map((ingredient) => ({
        ...ingredient,
      }));
    },
    sauces() {
      return this.pizza.sauces.map((sauce) => ({
        ...sauce,
      }));
    },
    sizes() {
      return this.pizza.sizes.map((size) => ({
        ...size,
      }));
    },
  },
};
</script>

<style lang="scss">
@import "~@/assets/scss/app";
</style>
