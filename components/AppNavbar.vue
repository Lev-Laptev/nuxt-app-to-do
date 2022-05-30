<template>
  <b-navbar>
    <template #brand>
      <b-navbar-item tag="router-link" :to="{ path: '/' }">
        <img
          src="~/assets/icons/timing.png"
          alt="to-do"
        >
      </b-navbar-item>
    </template>

    <template #start>
      <b-navbar-item
        tag="router-link"
        :to="{ path: '/' }"
      >
        Link 1
      </b-navbar-item>

      <b-navbar-item
        tag="router-link"
        :to="{ path: '/' }"
      >
        Link 2
      </b-navbar-item>
    </template>
  </b-navbar>
</template>

<script>
export default {
  name: 'AppNavbar'
}
</script>
