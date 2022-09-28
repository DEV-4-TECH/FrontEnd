<template>
  <div>
    <h1>This is an about page</h1>
    <pv-button @click="navigateToHome">Home</pv-button>
  </div>
</template>

<script>

export default {
  data() {
    return {}
  },
  methods: {
    navigateToHome() {
      this.$router.push('/home');
    }
  }
}

</script>
