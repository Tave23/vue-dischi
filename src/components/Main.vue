<template>
  <main>
     <CardList />
  </main>
</template>

<script>

import CardList from './CardList.vue';

export default {
   // gli si assegna il nome prima di importarlo
   name: "Main",
   components: {
      CardList
   }
}
</script>

<style scoped lang="scss">

@import "../assets/style/vars.scss";

main{
   height: calc(100vh - 75px);
   width: 100vw;
   background-color: $main-color;
   overflow-y: scroll;
}

</style>