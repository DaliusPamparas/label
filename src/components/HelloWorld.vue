<template>
  
    <div>
    <!-- SOURCE -->
   <b-container fluid >
    <b-row>
       <b-col>

        <b-row>
          <b-col>
           <span class="d-print cg2">CG2</span>
           
          </b-col>
          <b-col class="adresasTop">
             Shipper:   Symrise GmbH & Co.KG Muehlenfeldstr. 1, 37603 Holzminden / Germany
          </b-col>
        </b-row>
        <b-row>
          <b-col>
          
  <barcode v-bind:value="barcodeValue1" font-size='1px' height='30px' >
    
    Can't generate the barcode
  </barcode>
 <input v-model="barcodeValue1" class="barcode1input"  /><br> 
          </b-col>
          
        </b-row>
        
        <b-row>
          <b-col>
           <input v-model="produktoPavadinimas" class="produktas"  /><br/>
           <input v-model="produktoPavadinimas2" class="produktas"  />
          </b-col>
          
        </b-row>
        <b-row>
          <b-col class="mazasTextKairej">
            Für die Herstellung von Lebensmitteln bestimmt, nicht für den Verkauf Einzelhandel. 
          </b-col>
          
        </b-row>
        <b-row>
          <b-col >
            <textarea rows="6" cols="70"  v-model="adresasKaireje" class="adresasKairej"  >
Enter text here...</textarea> 
          </b-col>
          
        </b-row>
        <b-row>
          <b-col  cols="1" class="smallText">
            Simryse <br/>material <br> No:
          </b-col>
          <b-col>
           <input v-model="nr1" class="nrLeft"  />
          </b-col>
          
          <b-col  cols="1"  class="smallText">
           Lot:
          </b-col>
           <b-col>
           <input v-model="nr2" class="nrLeft"  />
          </b-col>
        </b-row>

       </b-col>





       <b-col>
         <b-row>
           <b-col><img src="@/assets/symrise.jpg" class="imageLogo"></b-col>
         </b-row>
         <b-row>
           <b-col>
<span class="smallText">Order:</span>
<input v-model="nr3" class="nrR"  />

<span class="smallText">Pos:</span>
<input v-model="nr4" class="nrR"  /><br>
<span class="smallText">kgs Net:</span>
<input v-model="nr5" class="nrR"  /><br>
<span class="smallText">kgs Tara:</span>
<input v-model="nr6" class="nrR"  />
<span class="smallText">kgs Gross:</span>
<input v-model="nr7" class="nrR"  /><br>
 <textarea rows="6" cols="30"  v-model="infoRighten" class="infoRight"  >
Enter text here...</textarea> 
           </b-col>
             <b-col   cols="3">
               <b-row>
                 <b-col>
<barcode v-bind:value="barcodeValue2" font-size='1px' height='120px'  class="transformCode">
                  </barcode>
                 </b-col>
               </b-row>
               <b-row>
                 <b-col>
                  <br> <br> <br> <br><br><br><br>  <input v-model="barcodeValue2" class="barcode1input"  />
                 </b-col>
               </b-row>
                  
            
             
              
           </b-col>
         </b-row>
       </b-col>
        
    </b-row>
</b-container>




    <!-- OUTPUT -->
   
   
  </div>
 
</template>

<script>

import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import VueBarcode from 'vue-barcode'



export default {
  name: 'HelloWorld',
  data() {
    return {
      barcodeValue1: '(00)340454570378149280',
      barcodeValue2: 'G 255789587888',
      produktoPavadinimas: 'Cia rasyt produkto pavadinima',
      produktoPavadinimas2: 'Country of origin: Germany',
      adresasKaireje: 'Firm address rasyt cia multiline',
      infoRighten: 'Storage ...',
      nr1: '555555',
      nr2: '7777',
      nr3: '77766',
      nr4: '77744',
      nr5: '7774',
      nr6: '7444',
      nr7: '2224',
    }
  },
  components: {
    'barcode': VueBarcode
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  lang="scss">
 $main-color: black;
 $border: solid $main-color 1px;
 $no-border:  0px solid ;

.cg2{
  border: $border;
  padding: 5px;
  font-size: 20px;
}
.adresasTop{
  font-size: 12px;
}

.barcode1input{
  font-size: 12px;
  text-align: center;
  border: $no-border;
  
}
.produktas{
  font-size: 22px;
  font-weight: bolder;
  width: 100%;
  border: $no-border;

}
.imageLogo{
  width: 200px;
  
}
.mazasTextKairej{
  font-size: 11px;
  padding-top: 50px;
  padding-bottom: 20px;
}
.smallText{
  
  font-size: 11px;
 

}
.adresasKairej{
  
  border: $no-border;
}
.nrLeft{
  font-size: 25px;
  font-weight: bolder;
  width: 200px;
  border: $no-border;
}
.nrR{
  font-size: 25px;
  font-weight: bolder;
  width: 100px;
  border: $no-border;
}
.transformCode{
  transform: rotate(90deg);
}
.barcodeInPut{
  margin-top: 700px;
}
.infoRight{
  background-color: lightgray;
  border: $no-border;
}
</style>
