<template>
  <section class="container">
    <h1>HOMEPAGE</h1>
  </section>
</template>

<script>
export default {
  transition() {
    return "slide";
  }
};
</script>

<style lang="scss">
.slide-enter-active {
  transition: all 0.3s ease-in-out;
}

.slide-leave-active {
  transition: all 0.3s ease-in-out;
}

.slide-enter {
  transform: translateY(-100%);
  opacity: 0;
}
.slide-enter-to {
  transform: translateY(0%);
  opacity: 1;
}

.slide-leave {
  transform: translateY(0);
  opacity: 1;
}
.slide-leave-to {
  transform: translateY(100%);
  opacity: 0;
}
</style>
