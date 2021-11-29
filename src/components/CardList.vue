<template>
   <div class="container text-center p-5">
      <div class="row">
         <div class="col-5 m-auto">
            <div class="box">

               <Select 
               @changeValue="filterGenr"/>

            </div>
         </div>
      </div>
      <div class="row">
         <div 
         v-if= "printed"
         class="box d-flex">

            <div 
            v-for= "singleCard in filterCharacters"
            :key= "singleCard.id"
            :singleCard= "singleCard"
            class="card-container">
               <img :src="singleCard.poster" alt="">
               <!-- titolo canzone -->
               <h5>{{singleCard.title}}</h5>
               <p>{{singleCard.author}}</p>
               <p>{{singleCard.year}}</p>
            </div>

         </div>

         <!-- loading -->
         <div v-else class="loading">
            <div class="lds-ring"><div></div><div></div><div></div><div></div></div>
         </div>

      </div>
   </div>
</template>

<script>

// importo axios
import axios from 'axios';
import Select from './Select.vue';

export default {
  components: { 
   Select 
   },
   // gli si assegna il nome prima di importarlo
   name: "CardList",
   data(){
      return{
         musicList: [],
         printed: false,

         genrType: ''
      }
   },
   methods:{
      startApi(){
         axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(response => {
               console.log(response);
               this.musicList = response.data.response;
               console.log(this.musicList);

               // quando ha stampato diventa true
               this.printed = true;
                
            })
            .catch(error => {
               console.log(error);
               
            })
            
      // funzione per filtrare 
      },
      filterGenr(selectedGenre){

         console.log('selectedGenre', selectedGenre)

         this.genrType =selectedGenre

         console.log('genrType', this.genrType)

         return this.genrType
      }
   },
   // faccio partire axios al caricamento della pagina
   mounted(){
      this.startApi();
   },
   computed:{
      filterCharacters(){
      if(this.genrType === "default"){
        return this.musicList
      }
      return this.musicList.filter(singleCard => {
        return singleCard.genre.includes(this.genrType)
      })
    }
   }
}
</script>

<style scoped lang="scss">

@import "../assets/style/vars.scss";

.box.d-flex{
   flex-wrap: wrap;
   justify-content: center;
}

.card-container{
   width: 15%;
   margin: 20px;
   padding: 10px ;
   background-color: $header-card-color;
}

.card-container:hover{
   color: grey;
   background-color: $hover-bg-color;
}

.card-container img{
   width: 70%;
   height: 60%;
   margin: 0 auto 10px;
   padding-bottom: 25px;
}

h5{
   text-transform: uppercase;
   color: white;
   font-size: 14px;
}

p{
   margin-bottom: -7px;
}

// loader

.loading{
   padding-top: 15%;
}

.lds-ring {
  display: inline-block;
  position: relative;
  width: 80px;
  height: 80px;
}
.lds-ring div {
  box-sizing: border-box;
  display: block;
  position: absolute;
  width: 64px;
  height: 64px;
  margin: 8px;
  border: 8px solid $header-card-color;
  border-radius: 50%;
  animation: lds-ring 1.2s cubic-bezier(0.5, 0, 0.5, 1) infinite;
  border-color: $header-card-color transparent transparent transparent;
}
.lds-ring div:nth-child(1) {
  animation-delay: -0.45s;
}
.lds-ring div:nth-child(2) {
  animation-delay: -0.3s;
}
.lds-ring div:nth-child(3) {
  animation-delay: -0.15s;
}
@keyframes lds-ring {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

</style>