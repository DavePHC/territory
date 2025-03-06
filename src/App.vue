<script lang="ts" setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <img alt="Territory logo" class="logo" src="@/assets/images/logo.svg" width="35" height="35" />
    <div class="wrapper">
      <nav class="navigation">
        <RouterLink to="/">Форма</RouterLink>
        <RouterLink to="/table">Данные</RouterLink>
      </nav>
    </div>
  </header>

  <main>
    <RouterView />
  </main>
</template>

<style scoped>
.logo {
  display: block;
  margin: 0 auto 2rem;
}

.navigation {
  display: flex;
  justify-content: center;
  gap: 20px;
}
</style>
