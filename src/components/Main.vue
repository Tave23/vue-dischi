<template>
  <main>
     ciao
  </main>
</template>

<script>
export default {
   // gli si assegna il nome prima di importarlo
   name: "Main"
}
</script>

<style scoped lang="scss">

@import "../assets/style/vars.scss";

main{
   height: calc(100vh - 75px);
   width: 100vw;
   background-color: $main-color;
}

</style>