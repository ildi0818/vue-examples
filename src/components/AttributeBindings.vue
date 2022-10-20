<!-- eslint-disable prettier/prettier -->
<!--
Here we are reactively binding element attributes / properties to the state.
The :title syntax is short for v-bind:title.
-->

<script>
export default {
  data() {
    return {
      message: "Hello World!",
      isRed: true,
      color: "green",
      bela: "2 forint a tulipán",
      ezPiros: true,
      backgroundColor: "purple",
    };
  },
  methods: {
    toggleRed() {
      this.isRed = !this.isRed;
    },
    toggleColor() {
      this.color = this.color === "green" ? "blue" : "green";
    },
    valtozzPirosra() {
      this.ezPiros = !this.ezPiros;
    },
    hatterValtoztatos() {
      this.backgroundColor =
        this.backgroundColor === "purple" ? "yellow" : "purple";
    },
  },
};
</script>

<template>
  <p>
    <span :title="message">
      Hover your mouse over me for a few seconds to see my dynamically bound
      title!
    </span>
  </p>

  <!--
  class bindings have special support for objects and arrays
  in addition to plain strings
  -->
  <p :class="{ red: isRed }" @click="toggleRed">
    This should be red... but click me to toggle it.
  </p>

  <!-- style bindings also support object and arrays -->
  <p :style="{ color }" @click="toggleColor">
    This should be green, and should toggle between green and blue on click.
  </p>

  <p>
    <span :title="bela">
      Ha az egérmutatót a mondat felé viszed és ott tartod kiírja Béla üzenetét!
    </span>
  </p>

  <p :class="{ red: ezPiros }" @click="valtozzPirosra">
    Kattints rám és más színű leszek.
  </p>

  <p :style="{ backgroundColor }" @click="hatterValtoztatos">
    Én is váltogatom a színemet.
  </p>
</template>

<style>
.red {
  color: red;
}
</style>
