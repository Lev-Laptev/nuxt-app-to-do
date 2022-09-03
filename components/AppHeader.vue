<template>
  <section class="hero is-small is-info">
    <div class="hero-body has-text-centered">
      <AppTitle>
        Task Board"
      </AppTitle>

      <AppSubtitle>
        Create a list of taskssfds
      </AppSubtitle>
    </div>
  </section>
</template>

<script>
import {
  AppSubtitle,
  AppTitle
}
  from '@/components/common'

export default {
  name: 'AppHeader',
  components: {
    AppSubtitle,
    AppTitle
  }
}
</script>
