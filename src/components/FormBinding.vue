<!--
We can create two-way bindings between state and form inputs using the v-model directive.
-->

<script>
export default {
  data() {
    return {
      text: 'Edit me',
      szoveg: 'Szerkessz engem',

      checked: true,
      bejelolve: true,

      checkedNames: ['Jack'],
      kipipaltNev: ['Béla'],

      picked: 'One',
      kivalasztva: 'Egy',

      selected: 'A',
      szelektalt: 'X',

      multiSelected: ['A'],
      multiszelektalt: ['SZ']
    }
  }
}
</script>

<template>
  <h2>Text Input</h2>
  <input v-model="text"> {{ text }}

  <h2>Szöveg bevitel</h2>
  <input v-model="szoveg"> {{ szoveg }}

  <h2>Checkbox</h2>
  <input type="checkbox" id="checkbox" v-model="checked">
  <label for="checkbox">Checked: {{ checked }}</label>

  <h2>Jelölő doboz</h2>
  <input type="checkbox" id="checkbox" v-model="bejelolve">
  <label for="checkbox">Bejelölve: {{ bejelolve }}</label>

  <!--
    multiple checkboxes can bind to the same
    array v-model value
  -->
  <h2>Multi Checkbox</h2>
  <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
  <label for="jack">Jack</label>
  <input type="checkbox" id="john" value="John" v-model="checkedNames">
  <label for="john">John</label>
  <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
  <label for="mike">Mike</label>
  <p>Checked names: <pre>{{ checkedNames }}</pre></p>

  <h2>Többszörös jelölő doboz</h2>
  <input type="checkbox" id="bela" value="Béla" v-model="kipipaltNev">
  <label for="bela">Béla</label>
  <input type="checkbox" id="joska" value="Józska" v-model="kipipaltNev">
  <label for="joska">Józska</label>
  <input type="checkbox" id="pista" value="Pista" v-model="kipipaltNev">
  <label for="pista">Pista</label>
  <input type="checkbox" id="piroska" value="Piroska" v-model="kipipaltNev">
  <label for="piroska">Piroska</label>
  <p>Kipipált név: <pre>{{ kipipaltNev }}</pre></p>

  <h2>Radio</h2>
  <input type="radio" id="one" value="One" v-model="picked">
  <label for="one">One</label>
  <br>
  <input type="radio" id="two" value="Two" v-model="picked">
  <label for="two">Two</label>
  <br>
  <span>Picked: {{ picked }}</span>

  <h2>Rádiógomb</h2>
  <input type="radio" id="egy" value="Egy" v-model="kivalasztva">
  <label for="egy">Egy</label>
  <br>
  <input type="radio" id="ketto" value="Kettő" v-model="kivalasztva">
  <label for="ketto">Kettő</label>
  <br>
  <span>Kiválasztva: {{ kivalasztva }}</span>


  <h2>Select</h2>
  <select v-model="selected">
    <option disabled value="">Please select one</option>
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
  <span>Selected: {{ selected }}</span>

  <h2>Szelektálás</h2>
  <select v-model="szelektalt">
    <option disabled value="">Kérjük szelektáljon</option>
    <option>X</option>
    <option>Y</option>
    <option>Z</option>
  </select>
  <span>Szelektált: {{ szelektalt }}</span>

  <h2>Multi Select</h2>
  <select v-model="multiSelected" multiple style="width:100px">
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
  <span>Selected: {{ multiSelected }}</span>

  <h2>Többszörösen szelektált</h2>
  <select v-model="multiszelektalt" multiple style="width:150px">
    <option>SZ</option>
    <option>LY</option>
    <option>DZ</option>
  </select>
  <span>Multiszelektált: {{ multiszelektalt }}</span>
</template>