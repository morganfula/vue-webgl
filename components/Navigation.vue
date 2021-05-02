<template>
  <section class="navigation">
    <nuxt-link to="/">Homepage</nuxt-link>
    <nuxt-link to="/about">About</nuxt-link>
  </section>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.navigation {
  font-size: 20px;
  padding: 40px;
  text-align: right;

  a {
    padding: 10px 20px;
    color: #fff;
    text-decoration: none;
    border: 1px solid #000;
    text-transform: uppercase;
  }
}

.navigation .nuxt-link-exact-active {
  border-color: #fff;
}
</style>
