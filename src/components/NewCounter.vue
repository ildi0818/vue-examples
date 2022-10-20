<script>
export default {
  data() {
    return {
      count: 0,
      szamol: 10,
      szoroz: 1
    };
  },
};
</script>

<template>
  {{ count }}
  <button @click="count++">Count</button>

  {{ szamol }}
  <button @click="szamol+=10">Számol</button>

  {{ szoroz }}
  <button @click="szoroz*=5">Szoroz 5-tel</button>
</template>