<template>
  <Header/>
  <div class="container">
    <Total/>
    <RevenusDépenses/>
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import Total from "./components/Total.vue"
  import RevenusDépenses from './components/RevenusDépenses.vue';

  export default {
    components: {
      Header,
      Total,
      RevenusDépenses,
    },
  }
</script>