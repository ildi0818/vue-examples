<!--
https://eugenkiss.github.io/7guis/tasks/#crud
-->

<script>
export default {
  data() {
    return {
      names: ["Emil, Hans", "Mustermann, Max", "Tisch, Roman"],
      selected: "",
      prefix: "",
      first: "",
      last: "",

      allatok: ["Dr., Bubo", "Maci, Laci", "Kacsa, Donald"],
      valasztott: "",
      elonev: "",
      keresztnev: "",
      vezeteknev: "",
    };
  },
  computed: {
    filteredNames() {
      return this.names.filter((n) =>
        n.toLowerCase().startsWith(this.prefix.toLowerCase())
      );
    },
    szurtAllatok() {
      return this.allatok.filter((bela) =>
        bela.toLowerCase().startsWith(this.elonev.toLowerCase())
      );
    },
  },
  watch: {
    selected(name) {
      [this.last, this.first] = name.split(", ");
    },
    valasztott(allat) {
      [this.vezeteknev, this.keresztnev] = allat.split(", ")
    }
  },
  methods: {
    create() {
      if (this.hasValidInput()) {
        const fullName = `${this.last}, ${this.first}`;
        if (!this.names.includes(fullName)) {
          this.names.push(fullName);
          this.first = this.last = "";
        }
      }
    },

    letrehoz(){
      if(this.ervenyesInput()) {
        const teljesNev = `${this.vezeteknev}, ${this.keresztnev}`;
        if (!this.allatok.includes(teljesNev)) {
          this.allatok.push(teljesNev);
          this.keresztnev = this.vezeteknev = "";
        }
      }
    },

    update() {
      if (this.hasValidInput() && this.selected) {
        const i = this.names.indexOf(this.selected);
        this.names[i] = this.selected = `${this.last}, ${this.first}`;
      }
    },

    frissit() {
      if(this.ervenyesInput() && this.valasztott) {
        const j = this.allatok.indexOf(this.valasztott);
        this.allatok[j] = this.valasztott = `${this.vezeteknev}, ${this.keresztnev}`;
      }
    },
    
    del() {
      if (this.selected) {
        const i = this.names.indexOf(this.selected);
        this.names.splice(i, 1);
        this.selected = this.first = this.last = "";
      }
    },

    torles() {
      if (this.valasztott) {
        const j = this.allatok.indexOf(this.valasztott);
        this.allatok.splice(j, 1);
        this.valasztott = this.keresztnev = this.vezeteknev = "";
      }
    },

    hasValidInput() {
      return this.first.trim() && this.last.trim();
    },

    ervenyesInput () {
      return this.keresztnev.trim() && this.vezeteknev.trim();
    },  
  },
};
</script>

<template>
  <div><input v-model="prefix" placeholder="Filter prefix" /></div>

  <select size="5" v-model="selected">
    <option v-for="name in filteredNames" :key="name">{{ name }}</option>
  </select>

  <label>Name: <input v-model="first" /></label>
  <label>Surname: <input v-model="last" /></label>

  <div class="buttons">
    <button @click="create">Create</button>
    <button @click="update">Update</button>
    <button @click="del">Delete</button>
  </div>

  <h2>Ez a mi crud-unk</h2>
  <div><input v-model="elonev" placeholder="Szűrés" /></div>

  <select size="5" v-model="valasztott">
    <option v-for="allat in szurtAllatok" :key="allat">{{ allat }}</option>
  </select>

  <label>Keresztnév: <input v-model="keresztnev" /></label>
  <label>Vezetéknév: <input v-model="vezeteknev" /></label>

  <div class="buttons">
    <button @click="letrehoz">Létrehoz</button>
    <button @click="frissit">Frissít</button>
    <button @click="torles">Töröl</button>
  </div>
</template>

<style>
* {
  font-size: inherit;
}

input {
  display: block;
  margin-bottom: 10px;
}

select {
  float: left;
  margin: 0 1em 1em 0;
  width: 14em;
}

.buttons {
  clear: both;
}

button + button {
  margin-left: 5px;
}
</style>