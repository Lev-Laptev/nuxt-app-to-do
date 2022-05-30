<template>
  <div>
    <section class="main-content columns">
      <div class="container-fluid column is-12">
        <app-navbar />
        <Nuxt />
      </div>
    </section>
  </div>
</template>

<script>
import AppNavbar from '@/components/AppNavbar.vue'

export default {
  name: 'DefaultLayout',

  components: {
    AppNavbar
  }
}
</script>
