<template>
  <app-nav></app-nav>
  <router-view />
</template>

<script>
import AppNav from "./components/UI/AppNav.vue";
export default {
  components: {
    AppNav,
  },
};
</script>

<style>
.wrapper {
  padding-top: 2rem;
}

.card-body__profile-descr {
  margin-bottom: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid rgba(0, 0, 0, 0.125);
}

.card-body__profile-descr:last-child {
  border-bottom: 0;
  margin-bottom: 0;
  padding-bottom: 0;
}
</style>
