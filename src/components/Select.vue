<template>
  <div>
     <select 
     id="select"
     class="form-select form-select-md mb-3" 
     aria-label=".form-select-lg example"
     v-model="selectedGenre"
     @change="$emit('changeValue', selectedGenre)">
         <option value="default" selected>Seleziona il genere musicale</option>
         <option value="Rock">Rock</option>
         <option value="Pop">Pop</option>
         <option value="Jazz">Jazz</option>
         <option value="Metal">Metal</option>
      </select>
  </div>
</template>

<script>


export default {
   name: 'Select',
   data(){
      return{
         selectedGenre: 'default',
      }
   },
   methods:{
      
   },
   mounted(){

   }
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