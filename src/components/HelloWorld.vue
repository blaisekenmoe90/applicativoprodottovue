<template>


<div class="row">

<div  class="carrello" style="margin-right:100px;">
   <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-handbag" viewBox="0 0 16 16">
  <path d="M8 1a2 2 0 0 1 2 2v2H6V3a2 2 0 0 1 2-2zm3 4V3a3 3 0 1 0-6 0v2H3.36a1.5 1.5 0 0 0-1.483 1.277L.85 13.13A2.5 2.5 0 0 0 3.322 16h9.355a2.5 2.5 0 0 0 2.473-2.87l-1.028-6.853A1.5 1.5 0 0 0 12.64 5H11zm-1 1v1.5a.5.5 0 0 0 1 0V6h1.639a.5.5 0 0 1 .494.426l1.028 6.851A1.5 1.5 0 0 1 12.678 15H3.322a1.5 1.5 0 0 1-1.483-1.723l1.028-6.851A.5.5 0 0 1 3.36 6H5v1.5a.5.5 0 1 0 1 0V6h4z"/>
</svg>({{carrello}})

 
  </div>
<div class="row2" v-on:click="submit">

  <div  > 

 <img v-bind:src="image" >
 
  </div><br><br>

<label><h4>{{marca}}</h4></label><br><br>
<h4 v-if=" inventaire > 50"> In Stock prezzo <span class="prezzo1">99,99 euro</span>  + CONSEGNA </h4>
<h4 v-else-if=" inventaire <= 50 && inventaire > 0 " ><b class="prix">Sconti 10,99 euro</b><br><br> 
<span>prezzo precedente </span><span class="prezzo2"> 99 euro </span> fino a <b class="prix">-89%</b>  + CONSEGNA</h4>
<h4 v-else > Out Stock</h4><br>

<h4>Colori Disponibili</h4>
<div> 
  <ul class="colors">
   <li v-for=" prodotti in prodotto" :key="prodotti.id"
   @mouseover="updateImage(prodotti.color)"
   class="color-circle"
   :style="{backgroundColor : prodotti.color}"></li>
  </ul>
</div>

</div>



<h4>Misura</h4>
<select id="selectedOpM" v-on:click="submit"  style="box-shadow:1px 2px 3px 2px gray; border-radius:10px;">
<option>S</option>
<option>M</option>
<option>L</option>
 <option>XL</option>
<option>XXL</option>
</select><br><br>


<h4>Quantita</h4> <select id="selectedOpQQ" v-on:click="submit" style="box-shadow:1px 2px 3px 2px gray;
border-radius:10px;" >
 
<option>1</option>
<option>2</option>
<option>3</option>
<option>4</option>
 <option>5</option>
<option>6</option>
</select><br><br>
<h4>Fabricazioni</h4>
<div v-for=" Fabricazione in DetailsFabbricazione" 
    :key="Fabricazione.id"> {{Fabricazione}}  
  </div><br><br>
<div><h4>Recenzioni</h4>
  <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-star-fill" viewBox="0 0 16 16">
  <path d="M3.612 15.443c-.386.198-.824-.149-.746-.592l.83-4.73L.173 6.765c-.329-.314-.158-.888.283-.95l4.898-.696L7.538.792c.197-.39.73-.39.927 0l2.184 4.327 4.898.696c.441.062.612.636.282.95l-3.522 3.356.83 4.73c.078.443-.36.79-.746.592L8 13.187l-4.389 2.256z"/>
</svg>
<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-star-fill" viewBox="0 0 16 16">
  <path d="M3.612 15.443c-.386.198-.824-.149-.746-.592l.83-4.73L.173 6.765c-.329-.314-.158-.888.283-.95l4.898-.696L7.538.792c.197-.39.73-.39.927 0l2.184 4.327 4.898.696c.441.062.612.636.282.95l-3.522 3.356.83 4.73c.078.443-.36.79-.746.592L8 13.187l-4.389 2.256z"/>
</svg>
  <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-star-fill" viewBox="0 0 16 16">
  <path d="M3.612 15.443c-.386.198-.824-.149-.746-.592l.83-4.73L.173 6.765c-.329-.314-.158-.888.283-.95l4.898-.696L7.538.792c.197-.39.73-.39.927 0l2.184 4.327 4.898.696c.441.062.612.636.282.95l-3.522 3.356.83 4.73c.078.443-.36.79-.746.592L8 13.187l-4.389 2.256z"/>
</svg>
<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-star-fill" viewBox="0 0 16 16">
  <path d="M3.612 15.443c-.386.198-.824-.149-.746-.592l.83-4.73L.173 6.765c-.329-.314-.158-.888.283-.95l4.898-.696L7.538.792c.197-.39.73-.39.927 0l2.184 4.327 4.898.696c.441.062.612.636.282.95l-3.522 3.356.83 4.73c.078.443-.36.79-.746.592L8 13.187l-4.389 2.256z"/>
</svg>
 
 <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-star-half" viewBox="0 0 16 16">
  <path d="M5.354 5.119 7.538.792A.516.516 0 0 1 8 .5c.183 0 .366.097.465.292l2.184 4.327 4.898.696A.537.537 0 0 1 16 6.32a.548.548 0 0 1-.17.445l-3.523 3.356.83 4.73c.078.443-.36.79-.746.592L8 13.187l-4.389 2.256a.52.52 0 0 1-.146.05c-.342.06-.668-.254-.6-.642l.83-4.73L.173 6.765a.55.55 0 0 1-.172-.403.58.58 0 0 1 .085-.302.513.513 0 0 1 .37-.245l4.898-.696zM8 12.027a.5.5 0 0 1 .232.056l3.686 1.894-.694-3.957a.565.565 0 0 1 .162-.505l2.907-2.77-4.052-.576a.525.525 0 0 1-.393-.288L8.001 2.223 8 2.226v9.8z"/>
</svg>
 

 
</div><br><br><br>
<div> 
  <button type="button"  v-on:click="submit"> Acquista</button>
 
</div>

</div>



</template>

<script>
export default {
  name: 'HelloWorld',
   data (){
     return {

       image:'./assets/images/vans1.jpg',

       title:'Applicativo Prodotto Scarpe',

       inventaire :10,

       marca:' Marca: Sang Royal',
      
       Misura:'selectedOpM',

       quantita:'selectedOpQ',

       DetailsFabbricazione:['90% cotton', '50% lana', '20% plastica'],

       prodotto:[
         { id:1,name:'SangRoayal', color:'black',image:'./assets/images/vans1.jpg',prezzo:10.99},
         { id:2,name:'SangRoayal' ,color:'white',image:'./assets/images/vans2.png',prezzo:90.99},
         { id:3,name:'SangRoayl',color:'red',image:'./assets/images/vans3.png',prezzo:10.99},
         { id:4,name:'SangRoayl',color:'blue',image:'./assets/images/vans4.png',prezzo:10.99},
     
       ],
       carrello:0,
       contenuto:[]
     }
     
   },
  props: {
    msg: String
  },
  methods:{

submit(){
    this.carrello +=1;
  },
seleted(){
  this.contenuto +=1;
}
}}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.row {
 width: 60%;
}
.prezzo1{
  color:rgb(3, 0, 196);
  font-size: 20px; 
}
.prezzo2{
text-decoration:line-through rgb(255, 44, 20);
}
.prix{
  color: red;
}
.carrello {
  margin-left: 850px;
  border: 1px solid black;
  height: 40px;
  width: 20%;
  padding: 10px;
  border-radius: 5px;
  box-shadow: 2px 1px 2px 1px;
  background: rgb(73, 195, 73);
  font-size: 18px;
}
.ul{
  float: right;
  margin: 150px; 
} 
ul li{
  display: inline-block;
  padding: 5px 20px;
}
.color-circle{
  width: 50px;
  height: 50px;
  margin-top: 8px;
  border: 1px solid black;
  border-radius: 50%;
  margin: 7px;
}
button{
  background-color: rgb(12, 12, 213);
  color: white;
  font-size: 20px;
  border-radius: 10px;
  padding: 15px;
}
.images{
  height: 300px;
  width: 100%;
}
.row2{
  border: 1px solid black;
  border-radius: 15px;
  box-shadow: 1px 2px 3px 2px rgb(160, 159, 159);
}
.row2:hover:hover{
  background-color: rgb(138, 229, 211);
}
img{
  font-size: 100%;
  width: 100px;
}
</style>
<!--
realizzare una pagina che legge i dati da un file json o direttamente da un file  js se preferisci 

che contiene un elenco di prodotti.

Per ogni prodotto è definito: 

SKU: il codice del prodotto

name: il nome del prodotto

qnty: la quantità

price: il prezzo del prodotto

 

realizzare una  applicativo che mostra il primo prodotto e mostra un tasto per aquistare vicino ad una casella di testo in cui si può scrivere una quantità.

 

quando si preme il tasto per acquistare il  codice del prodotto viene inserito in un carrello

nella pagina del prodotto sono presenti anche due frecce per andare al prodotto successivo e al precedente

inoltre vi è una pagina che porta al carrello

quando si visualizza il carrello si vede l'elenco dei prodotti presenti e per ognuni la quantità presente nel carrello e il prezzo 

inoltre viene mostrato il prezzo totale

-->