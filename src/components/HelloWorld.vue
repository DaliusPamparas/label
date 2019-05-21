<template>
  <div>
    <!-- SOURCE -->
    <b-container>
      <b-row>
        <b-col cols="6">
          <b-row>
            <b-col cols="2">
              <span class="cg2">CG2</span>
            </b-col>
            <b-col class="adresasTop">
              <span class="beforeaddress align-top">Shipper:</span>
              <div class="adresas">
                Symrise GmbH & Co.
                <br>KG Muehlenfeldstr. 1,
                <br>37603 Holzminden / Germany
                <br>
              </div>
            </b-col>
          </b-row>
          <b-row>
            <b-col>
              <barcode
                v-bind:value="barcodeValue1"
                font-size="1px"
                display-value="false"
                width="2"
                height="30"
                margin-bottom="1"
              >Can't generate the barcode</barcode>
            </b-col>
          </b-row>
          <b-row>
            <b-col class="text-center">
              <input v-model="barcodeValue1" class="barcode1input h-50">
              <br>
            </b-col>
            <b-col cols="2"></b-col>
          </b-row>

          <b-row>
            <b-col>
              <input v-model="produktoPavadinimas" class="produktas text-uppercase">
              <br>
              <input v-model="produktoPavadinimas2" class="produktas">
            </b-col>
          </b-row>
          <b-row>
            <b-col class="leftTextSmall1">
              Kuhl und trocken lagern.
              <br>Dicht versehlossen halten.
            </b-col>
          </b-row>
          <b-row>
            <b-col class="mazasTextKairej">Fur Legensmittel. Nicht fur den Verkauf im Einzelhandel.</b-col>
          </b-row>
          <b-row>
            <b-col class="hozLine"></b-col>
          </b-row>
          <b-row>
            <b-col>
              <textarea rows="4" cols="50" v-model="adresasKaireje" class="adresasKairej">
Th. Geyer Ingredients Gmbh & Co. Kg</textarea>
            </b-col>
          </b-row>
          <b-row>
            <b-col cols="1" class="smallText">
              Simryse
              <br>material
              <br>No:
            </b-col>
            <b-col>
              <input v-model="nr1" class="nrLeft">
            </b-col>

            <b-col class="smallText">
              <span class="smallText">Lot:</span>
              <br>
              <input v-model="nr2" class="nrRight">
            </b-col>
          </b-row>
        </b-col>

        <b-col>
          <b-row>
            <b-col class="text-right">
              <img src="@/assets/symrise.jpg" class="imageLogo">
            </b-col>
          </b-row>
          <b-row>
            <b-col>
              <b-row>
                <b-col class="leftLine">
                  <span class="smallText align-top">Order:</span>
                  <input v-model="nr3" class="nrOrder">
                </b-col>
                <b-col>
                  <span class="smallText align-top">Pos:</span>
                  <input v-model="nr4" class="nrLeft nrPos">
                </b-col>
              </b-row>
<b-row>
            <b-col class="hozLine leftLine"></b-col>
          </b-row>
 <b-row>
            
            <b-col class="leftLine">
              <span class="smallText align-top">kgs Net:</span>
              <input v-model="nr5" class="nrR">
            </b-col>
          </b-row>
<b-row>
            <b-col class="hozLine leftLine"></b-col>
          </b-row >
          <b-row>
            <b-col class="leftLine">
              <span class="smallText align-top">kgs Tara:</span>
              <input v-model="nr6" class="nrR">
            </b-col>
            <b-col>
 <span class="smallText align-top">kgs Gross:</span>
              <input v-model="nr7" class="nrR">
            </b-col>
          </b-row>

          <b-row>
            <b-col class="hozLine leftLine"></b-col>
          </b-row>
<b-row>
  <b-col class="area leftLine">
    <textarea rows="4" cols="38" v-model="infoRighten" class="infoRight">
Enter text here...</textarea>
  </b-col>
</b-row>
<b-row>
            <b-col class="hozLine"></b-col>
          </b-row>
           <b-row>
            
            <b-col class="leftLine">
              <span class="smallText align-top">Customer order No.</span>
              <span class="customer">620669</span>
            </b-col>
          </b-row>
<b-row>
            <b-col class="hozLine leftLine"></b-col>
          </b-row>
           <b-row>
            
            <b-col class="leftLine">
              <span class="smallText align-top">Customer Mat. No.</span>
              <input  class="nrR2">
            </b-col>
          </b-row>
<b-row>
            <b-col class="hozLine leftLine"></b-col>
          </b-row>
          <b-row>
            <b-col class="leftLine">
               <input v-model="barcodeValue2" class="barcode1input barcode2input">
            </b-col>
          </b-row>
          <b-row>
            <b-col>
              <barcode
                    v-bind:value="barcodeValue2"
                    display-value="false"
                width="2"
                height="60"
                margin-bottom="1"
                  ></barcode>
            </b-col>
          </b-row>
          

            </b-col>
            <b-col class="barcode2transf "  cols="3">
             
                  <barcode
                    v-bind:value="barcodeValue2"
                     display-value="false"
                    width="2"
                height="100"
                    class="transformCode"
                  ></barcode></b-col>
          </b-row>
          
         
        </b-col>
      </b-row>
    </b-container>

    <!-- OUTPUT -->
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";
import VueBarcode from "vue-barcode";

export default {
  name: "HelloWorld",
  data() {
    return {
      barcodeValue1: "(00)340454570378149280",
      barcodeValue2: "G 255789587888",
      produktoPavadinimas: "Cia rasyt produkto pavadinima",
      produktoPavadinimas2: "Country of origin: Germany",
      adresasKaireje: "Th Geyer Ingrediens Gmbh & co.kg",
      infoRighten: "Storage ...",
      nr1: "555555",
      nr2: "234565",
      nr3: "77766",
      nr4: "2",
      nr5: "7774",
      nr6: "7444",
      nr7: "2224"
    };
  },
  components: {
    barcode: VueBarcode
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hozlinija {
  padding-right: 10px;
  border-left: 1px black solid;
}

.cg2 {
  border: solid black 1px;
  margin: 5px;
  font-size: 22px;
  padding: 5px;
}

.adresas {
  display: inline-block;
}
.adresasTop {
  font-size: 11px;
  line-height: 12px;
}

.barcode1input {
  line-height: 10px;
  font-size: 12px;
  text-align: center;
  border: 0px solid;
  margin-top: 0px;
  padding-top: 0px;
}
.barcode2input{
  line-height: 14px;
  font-size: 15px;
  text-align: right;
  border: 0px solid;
  margin-top: 130px;
  padding-top: 20px;
}
.produktas {
  font-size: 20px;
  font-weight: bolder;
  width: 100%;
  border: 0px solid;
}
.imageLogo {
  width: 250px;
}
.leftTextSmall1 {
  font-size: 9px;
  padding-top: 90px;
  padding-bottom: 40px;
}
.mazasTextKairej {
  font-size: 11px;

  padding-bottom: 20px;
}
.smallText {
  font-size: 11px;
}
.hozLine {
  border-top: 1px black solid;
}
.adresasKairej {
  border: 0px solid;
  font-size: 20px;
  padding-top: 30px;
  padding-bottom: 90px;
}
.nrLeft {
  padding-top: 4px;
  font-size: 38px;
  font-weight: bolder;
  width: 170px;
  border: 0px solid;
}
.nrOrder{
  height: 30px;
  font-size: 38px;
  font-weight: bolder;
  line-height: 18px;
  border: 0px solid;
  width: 170px;
  
}
.nrRight {
  height: 30px;
  font-size: 38px;
  font-weight: bolder;
  line-height: 18px;
  border: 0px solid;
  width: 170px;
}
.nrPos{
  height: 30px;
  font-size: 38px;
  font-weight: bolder;
  line-height: 18px;
  border: 0px solid;
  width: 30px;
}
.nrR {
  font-size: 18px;
  font-weight: bolder;
  width: 70px;
  border: 0px solid;
}
.nrR2{
   font-size: 18px;
  font-weight: bolder;
  width: 70px;
  border: 0px solid;
  padding-top: 0px;
}
.customer{
  font-size: 24px;
  color: black;
}
.transformCode {
  transform: rotate(90deg);
}
.barcodeInPut {
  margin-top: 700px;
}
.infoRight {
  background-color: rgb(236, 236, 236);
  border: 0px solid;
}
.area{
  background-color: rgb(236, 236, 236);
}
.leftLine{
  border-left: 1px black solid;
}

</style>
