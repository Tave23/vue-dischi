<template>
  <div>
     <select 
     class="form-select form-select-md mb-3" 
     aria-label=".form-select-lg example">
         <option value="1">Rock</option>
         <option value="2">Pop</option>
         <option value="3">Jazz</option>
         <option value="4">Metal</option>
      </select>
  </div>
</template>

<script>


export default {
   name: 'Select',

   methods:{
      
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