<template>
  <header>
      <div class="box-logo">
         <img src="../assets/logo.png" alt="Logo">
      </div>
  </header>
</template>

<script>

export default {
   // gli si assegna il nome prima di importarlo
   name: "Header",
   components: {
  },
  data(){
     return{
      
     }
  },
  methods:{
   
  }
}
</script>

<style scoped lang="scss">

@import "../assets/style/vars.scss";

header{
   height: 75px;
   width: 100vw;
   background-color: $header-card-color;
   line-height: 75px;
   padding-left: 10px;
   display: flex;
   justify-content: space-between;
}

.box-logo{
   width: 5%;
}

.box-logo img{
   width: 100%;
}

</style>

   


