<!--
Here we show the simplest possible component which accepts a prop and renders it.
Learn more about components in the guide!
-->

<script>
import TodoItem from "./TodoItem.vue";
import EzAMiPropsunk from "./EzAMiPropsunk.vue";
import MegEgyProps from "./MegEgyProps.vue";

export default {
  components: {
    TodoItem,
    EzAMiPropsunk,
    MegEgyProps,
  },
  data() {
    return {
      groceryList: [
        { id: 0, text: "Vegetables" },
        { id: 1, text: "Cheese" },
        { id: 2, text: "Whatever else humans are supposed to eat" },
      ],

      zoldseglista: [
        { id: 0, szoveg: "Paradicsom" },
        { id: 1, szoveg: "Répa" },
        { id: 2, szoveg: "Burgonya" },
      ],

      nevek: [
        { id: 0, nev: "Ági" },
        { id: 1, nev: "Margit" },
        { id: 2, nev: "Jázmin" },
      ],
    };
  },
};
</script>

<template>
  <ol>
    <!--
      We are providing each todo-item with the todo object
      it's representing, so that its content can be dynamic.
      We also need to provide each component with a "key",
      which is explained in the guide section on v-for.
    -->
    <TodoItem
      v-for="item in groceryList"
      :todo="item"
      :key="item.id"
    ></TodoItem>
  </ol>

  <ol>
    <EzAMiPropsunk
      v-for="darab in zoldseglista"
      :tennivalok="darab"
      :key="darab.id"
    ></EzAMiPropsunk>
  </ol>

  <ol>
    <MegEgyProps 
      v-for="nev in nevek" 
      :nevek="nev" 
      :key="nev.id"
    ></MegEgyProps>
  </ol>
</template>