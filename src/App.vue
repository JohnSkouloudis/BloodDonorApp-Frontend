<script setup>
import { onBeforeMount } from 'vue';
import { RouterView } from 'vue-router';
import { useApplicationStore as useUserStore } from '@/stores/user.js';
import AppHeader from '@/components/AppHeader.vue';

const { loadUserData } = useUserStore();

onBeforeMount(() => {
  loadUserData();
});

</script>

<template>
  <h1 class="position-absolute top-0 start-0">Blood Donor App</h1>
  <AppHeader />
  <RouterView />
</template>

<style scoped>

h1{
  color: #f2f2f2;
}

header {
  line-height: 1.5;
  max-height: 100vh;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a{
  color: var(--color-text);
}

nav a:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }


  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
