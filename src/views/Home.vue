<template>
  <div id="home" class="wrapper">
    <div class="container">
      <h1 class="mb-4">Portfolio</h1>

      <div class="row">
<app-form></app-form>
<app-portfolio></app-portfolio>

      </div>
    </div>
  </div>
</template>

<script>
import AppForm from '@/components/AppForm.vue'
import AppPortfolio from '@/components/AppPortfolio.vue'

export default {
 components: {
   AppForm,
   AppPortfolio
 }
};
</script>
