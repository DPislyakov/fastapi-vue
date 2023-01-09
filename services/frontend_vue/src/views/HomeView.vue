<template>
  <section>
    <p>Данный сайт был создан посредством 2 фреймворков FastApi и Vue.</p>

    <div v-if="isLoggedIn" id="logout">
      <p id="logout"><a href="/dashboard">Просмотреть</a> все записи</p>
    </div>
    <p v-else>
      <span><a href="/register">Регистрация</a></span>
      <span> или </span>
      <span><a href="/login">Войти</a></span>
    </p>
  </section>
</template>

<script>

import { defineComponent } from 'vue';

export default defineComponent({
  name: "HomeView",
  computed: {
    isLoggedIn: function() {
      return this.$store.getters.isAuthenticated;
    }
  },
});
</script>
