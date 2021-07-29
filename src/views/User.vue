<template>
  <div>
      <Header />
      <user />
  </div>
</template>

<script>
import user from '../components/User.vue'
import Header from '../components/Header'
export default {
    name: "User",
    components: {
        user,
        Header
    }
}
</script>

<style>

</style>