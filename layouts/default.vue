<template>
  <div class="layout">
    <div class="layout__content">
      <Nuxt />
    </div>
    <div class="layout__navigation">
      <Navigation />
    </div>
  </div>
</template>

<script>
import Navigation from "@/components/Navigation.vue";

export default {
  components: {
    Navigation
  }
};
</script>

<style lang="scss">
body {
  background: #000;
  font-family: Helvetica, sans-serif;
  overflow: hidden;
}

.layout {
  &__navigation {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
  }

  &__content {
    font-size: 140px;
    font-weight: bold;
    color: #fff;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;

    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
}

//? TRANSITION
.flip-enter-active {
  transition: all 0.3s ease-in-out;
}

.flip-leave-active {
  transition: all 0.3s ease-in-out;
}

.flip-enter {
  transform: translateY(-100%);
  opacity: 0;
}
.flip-enter-to {
  transform: translateY(0%);
  opacity: 1;
}

.flip-leave {
  transform: translateY(0);
  opacity: 1;
}
.flip-leave-to {
  transform: translateY(100%);
  opacity: 0;
}
</style>
