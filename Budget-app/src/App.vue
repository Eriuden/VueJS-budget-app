<template>
  <Header/>
  <div class="container">
    <Total/>
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import Total from "./components/Total.vue"

  export default {
    components: {
      Header,
      Total
    },
  }
</script>