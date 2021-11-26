<template>
   <div class="container text-center p-5">
      <div class="row">
         <div class="box d-flex">

            <div 
            v-for="singleCard in musicList"
            :key="singleCard.id"
            :singleCard="singleCard"
            class="card-container">
               <img :src="singleCard.poster" alt="">
            </div>

         </div>
      </div>
   </div>
</template>

<script>

// importo axios
import axios from 'axios';

export default {
   // gli si assegna il nome prima di importarlo
   name: "CardList",
   data(){
      return{
         musicList: []
      }
   },
   methods:{
      startApi(){
         axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(response => {
               console.log(response);
               this.musicList = response.data.response;
               console.log(this.musicList);
                
            })
            .catch(error => {
               console.log(error);
            })
            
      }
   },
   // faccio partire axios al caricamento della pagina
   mounted(){
      this.startApi();
   },
   props:{
      singleCard: Object
   }
}
</script>

<style scoped lang="scss">

@import "../assets/style/vars.scss";

.box.d-flex{
   flex-wrap: wrap;
}

.card-container{
   width: 15%;
   margin: 20px;
   padding: 10px ;
   background-color: $header-card-color;
}

.card-container img{
   width: 70%;
   margin: 0 auto;
}

</style>