<!--
This example demonstrates handling user input with the v-on directive.
-->

<script>
export default {
  data() {
    return {
      message: 'Hello World!',
      bela: 'visszafele beszélek!!'
    }
  },
  methods: {
    reverseMessage() {
      this.message = this.message.split('').reverse().join('')
    },
    reverseBela() {
      this.bela = this.bela.split('').reverse().join('')
    },
    notify() {
      alert('navigation was prevented.')
    }
  }
}
</script>

<template>
  <!--
    Note we don't need .value inside templates because
    refs are automatically "unwrapped" in templates.
  -->
  <h1>{{ message }}</h1>
  <h2>{{ bela }}</h2>

  <!--
    Bind to a method/function.
    The @click syntax is short for v-on:click.
  -->
  <button @click="reverseMessage">Reverse Message</button>
  <button @click="reverseBela">Reverse Bela</button>

  <!-- Can also be an inline expression statement -->
  <button @click="message += '!'">Append "!"</button>
  <button @click="bela += 'Béla'">Append "Béla"</button>

  <!--
    Vue also provides modifiers for common tasks
    such as e.preventDefault() and e.stopPropagation()
  -->
  <a href="https://vuejs.org" @click.prevent="notify">
    A link with e.preventDefault()
  </a>
</template>

<style>
button, a {
  display: block;
  margin-bottom: 1em;
}
</style>