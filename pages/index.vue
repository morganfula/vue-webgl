<template>
  <section class="container">
    <h1>HOMEPAGE</h1>
  </section>
</template>

<script>
import { TimelineMax } from "gsap";

export default {
  transition: {
    name: "test",
    mode: "out-in",
    css: false,
    enter: function(el, done) {
      let tl = new TimelineMax();
      tl.set(el, { y: 100, opacity: 0 });
      tl.to(el, 0.3, { y: 0, opacity: 1 });
      done();
    },
    leave: function(el, done) {
      let tl = new TimelineMax();
      tl.to(el, 0.3, { y: 100, opacity: 0 });
      done();
    }
  }
};
</script>

<style lang="scss"></style>
