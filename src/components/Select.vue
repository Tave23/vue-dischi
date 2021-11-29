<template>
  <div>
     <select 
     id="select"
     class="form-select form-select-md mb-3" 
     aria-label=".form-select-lg example"
     @change="getValue">
         <option value="1">Seleziona il genere musicale</option>
         <option value="2">Rock</option>
         <option value="3">Pop</option>
         <option value="4">Jazz</option>
         <option value="5">Metal</option>
      </select>
  </div>
</template>

<script>


export default {
   name: 'Select',

   methods:{
      getValue(){

         let select = document.getElementById('select');
         console.log(select.value);
      }
   },
   mounted(){
      
   },
}

</script>

<style lang="scss" scoped>

div{
   padding-right: 30px;
   padding-top: 15px;
   display: flex;
   justify-content: center;
   align-items: center;
   
}

</style>