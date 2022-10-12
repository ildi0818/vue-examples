<!--
We can render content conditionally or in a loop with the v-if and v-for directives.
-->

<script>
export default {
  data() {
    return {
      show: true,
      list: [1, 2, 3],

      words: ["béla", "jóska", "pista", "mariska"],
      newWords: ["volvo", "opel", "trabant"]
    }
  }
}
</script>

<template>
  <button @click="show = !show">Toggle List</button>
  <button @click="list.push(list.length + 1)">Push Number</button>
  <button @click="list.pop()">Pop Number</button>
  <button @click="list.reverse()">Reverse List</button>

  <ul v-if="show && list.length">
    <li v-for="item of list">{{ item }}</li>
  </ul>
  <p v-else-if="list.length">List is not empty, but hidden.</p>
  <p v-else>List is empty.</p>

    <!-- **************************************** -->
  <button @click="show = !show">Word List</button>
  <button @click="words.push(newWords.length + 1)">Push word</button>


  <ul v-if="show && words.length">
    <li v-for="word of words">{{ word }}</li>
    <!-- <li v-for="newWord of newWords">{{ newWord }}</li> -->
  </ul>

</template>