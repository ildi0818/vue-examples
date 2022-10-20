<!-- eslint-disable prettier/prettier -->
<script>
import PeldaFeladat from './components/PeldaFeladat.vue'
import AttributeBindings from './components/AttributeBindings.vue'
import ConditionalsAndLoops from './components/ConditionalsAndLoops.vue'
import FormBinding from './components/FormBinding.vue'
import PropsBeillesztese from './components/PropsBeillesztese.vue'
import MarkdownEditor from './components/MarkdownEditor.vue'
import GridAndSortAndFilter from './components/GridAndSortAndFilter.vue'
import NewCounter from './components/NewCounter.vue'
import TemperatureConverter from './components/TemperatureConverter.vue'
import NewCrud from './components/NewCrud.vue'

export default {
  data() {
    return {
      message: 'Hello World!',
      bela: 'Üzenet Bélától',
      marcsi: 'Levél Marcsitól'
    }
  },
  components: {
    PeldaFeladat,
    AttributeBindings,
    ConditionalsAndLoops,
    FormBinding,
    PropsBeillesztese,
    MarkdownEditor,
    GridAndSortAndFilter,
    NewCounter,
    TemperatureConverter,
    NewCrud
    }
}
</script>

<template>
  <h1>ALAP FELADAT</h1>
  <h1>{{ message }}</h1>
  <h2>{{ bela }}</h2>
  <h3>{{ marcsi }}</h3>

  <h1>PÉLDA FELADAT</h1>
  <pelda-feladat />

  <h1>ATTRIBUTE BINDINGS</h1>
  <attribute-bindings />

  <h1>CONDITIONALS AND LOOPS</h1>
  <conditionals-and-loops />

  <h1>FORM BINDING</h1>
  <form-binding />

  <h1>PROPS BEILLESZTÉSE</h1>
  <props-beillesztese />

  <h1>MARKDOWN EDITOR</h1>
  <markdown-editor />

  <h1>GRID AND SORT AND FILTER</h1>
  <grid-and-sort-and-filter />

  <h1>COUNTER</h1>
  <new-counter />

  <h1>TEMPERATURE CONVERTER</h1>
  <temperature-converter />

  <h1>CRUD</h1>
  <new-crud />
</template>
