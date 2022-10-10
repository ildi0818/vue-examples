<script>
import PeldaFeladat from './components/PeldaFeladat.vue'
import AttributeBindings from './components/AttributeBindings.vue'

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
    AttributeBindings
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
</template>