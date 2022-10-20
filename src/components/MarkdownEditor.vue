<!--
A simple markdown editor.
-->

<!-- <script>
import { marked } from 'marked'
import { debounce } from 'lodash-es'

export default {
  data: () => ({
    input: '# hello',
    szoveg: '# akarmi'
  }),
  computed: {
    output() {
      return marked(this.input)
    },
    kimenet() {
        return marked(this.szoveg)
      } 
  },
  methods: {
    update: debounce(function (e) {
      this.input = e.target.value
    }, 100),
    
    frissit: debounce(function (e) {
      this.szoveg = e.target.value
    }, 100)
  }
}
</script>

<template>
  <div class="editor">
    <textarea class="input" :value="input" @input="update"></textarea>
    <textarea class="input" :value="szoveg" @szoveg="frissit"></textarea>
    <div class="output" v-html="output"></div>
    <div class="kimenet" v-html="kimenet"></div>
  </div>
</template>

<style>
body {
  margin: 0;
}

.editor {
  height: 100vh;
  display: flex;
}

.input,
.output,
.szoveg{
  overflow: auto;
  width: 50%;
  height: 100%;
  box-sizing: border-box;
  padding: 0 20px;
}

.input {
  border: none;
  border-right: 1px solid #ccc;
  resize: none;
  outline: none;
  background-color: #f6f6f6;
  font-size: 14px;
  font-family: 'Monaco', courier, monospace;
  padding: 20px;
}

code {
  color: #f66;
}
</style> -->