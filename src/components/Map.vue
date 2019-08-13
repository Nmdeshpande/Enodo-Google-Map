<template>
  <v-container>
    <div id="map" style="border: solid 1px rgb(201, 201, 201);" class></div>

    <v-layout row class="mt-2">
      <v-btn color="info" @click="applyFilters()">Apply Filters</v-btn>
      <v-btn color="success" @click="clearFilters()">Clear Filters</v-btn>
    </v-layout>

    <v-layout row wrap class="mt-2">
      
        <v-flex xs12 sm6 md4>
        <v-select
          :items="fulladdress"
          v-model="full_address"
          box
          label="Full Address"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md2>
        <v-select
          :items="zipitm"
          v-model="zipSelected"
          box
          label="Zipcode"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md3>
     
       <v-select
          :items="LatitudeonLoad"
          v-model="latitude"
          box
          label="Latitude"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>
      <v-flex xs12 sm6 md3>
     

             <v-select
          :items="LongLoad"
          v-model="longitude"
          box
          label="Longitude"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
        
      </v-flex>

      <!-- Second Row Start -->
      <v-flex xs12 sm6 md2>
        <v-select
          :items="recItems"
          v-model="recSelected"
          box
          label="Rec_Type"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>
      <v-flex xs12 sm6 md3>



<v-select
          :items="Pincode"
          v-model="pin"
          box
          label="Pin"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>

      <v-flex xs12 sm6 md2>
        <v-select
          :items="OVACLScode"
          v-model="ovaclsSelected"
          box
          label="OVACLS"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md5>
        <v-select
          :items="class_descriptionItems"
          v-model="class_descriptionSelected"
          box
          label="Class Description"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <!-- Third Row -->
      <v-flex xs12 sm6 md3>
             <v-select
          :items="minCurrent_Land"
          v-model="minCurrentLand"
          box
          label="Min Current Land"
          color="success"
          class="ml-1 mr-1"
        ></v-select>




      </v-flex>
      <v-flex xs12 sm6 md3>

      <v-select
          :items="minCurrent_Land"
          v-model="maxCurrentLand"
          box
          label="Max Current Land"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md3>
      <v-select
          :items="minCurrent_Building"
          v-model="minCurrentBuilding"
          box
          label="Min Current Building"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>
      <v-flex xs12 sm6 md3>

 <v-select
          :items="minCurrent_Building"
          v-model="maxCurrentBuilding"
          box
          label="Min Current Building"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>

      <v-flex xs12 sm6 md3>

 <v-select
          :items="Min_Current_Total"
          v-model="minCurrentTotal"
          box
          label="Min Current Total"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      
      </v-flex>
      <v-flex xs12 sm6 md3>
       <v-select
          :items="Min_Current_Total"
          v-model="maxCurrentTotal"
          box
          label="Max Current Total"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md3>

   <v-select
          :items="ESTIMATED_MARKET_VALUE"
          v-model="minEstimatedMarketValue"
          box
          label="Min Estimated Market Value"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>
      <v-flex xs12 sm6 md3>

 <v-select
          :items="ESTIMATED_MARKET_VALUE"
          v-model="maxEstimatedMarketValue"
          box
          label="Max Estimated Market Value"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>

      <v-flex xs12 sm6 md3>

      <v-select
          :items="PRIOR_LAND"
          v-model="minPriorLand"
          box
          label="Min Prior Land"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>
      <v-flex xs12 sm6 md3>

   <v-select
          :items="PRIOR_LAND"
          v-model="maxPriorLand"
          box
          label="Max Prior Land"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>

      <v-flex xs12 sm6 md3>


<v-select
          :items="PRIOR_BUILDING"
          v-model="minPriorBuilding"
          box
          label="Min Prior Building"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

     
      </v-flex>
      <v-flex xs12 sm6 md3>



<v-select
          :items="PRIOR_BUILDING"
          v-model="maxPriorBuilding"
          box
          label="Max Prior Building"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>

      <v-flex xs12 sm6 md3>



<v-select
          :items="PPRIOR_TOTAL"
          v-model="minPriorTotal"
          box
          label="Min Prior Total"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      
      </v-flex>
      <v-flex xs12 sm6 md3>


<v-select
          :items="PPRIOR_TOTAL"
          v-model="maxPriorTotal"
          box
          label="Max Prior Total"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      
      </v-flex>

      <v-flex xs12 sm6 md3>
<v-select
          :items="PPRIOR_LAND"
          v-model="minPPriorLand"
          box
          label="Min PPrior Land"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>


      <v-flex xs12 sm6 md3>

<v-select
          :items="PPRIOR_LAND"
          v-model="maxPPriorLand"
          box
          label="Max PPrior Land"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

        
      </v-flex>

      <v-flex xs12 sm6 md3>


<v-select
          :items="PPRIOR_BUILDING"
          v-model="minPPriorBuilding"
          box
          label="Min PPrior Building"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

       
      </v-flex>
      <v-flex xs12 sm6 md3>

      <v-select
          :items="PPRIOR_BUILDING"
          v-model="maxPPriorBuilding"
          box
          label="Max PPrior Building"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      
      </v-flex>

      <v-flex xs12 sm6 md3>


      <v-select
          :items="PPRIOR_TOTAL"
          v-model="minPPriorTotal"
          box
          label="Min PPrior Total"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>
      <v-flex xs12 sm6 md3>


 <v-select
          :items="PPRIOR_TOTAL"
          v-model="maxPPriorTotal"
          box
          label="Max PPrior Total"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

       
      </v-flex>

      <v-flex xs12 sm6 md3>



 <v-select
          :items="PPRIOR_YEAR"
          v-model="minPPriorYear"
          box
          label="Min PPrior Year"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>
      <v-flex xs12 sm6 md3>

 <v-select
          :items="PPRIOR_YEAR"
          v-model="maxPPriorYear"
          box
          label="Max PPrior Year"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      
   
      </v-flex>

      <v-flex xs12 sm4 md2>



        <v-select
          :items="TOWN"
          v-model="townSelected"
          box
          label="Town"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md2>
        <v-select
          :items="VOLUME"
          v-model="volumeSelected"
          box
          label="Volume"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md2>
        <v-select
          :items="LOC"
          v-model="locSelected"
          box
          label="Loc"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md2>
        <v-select
          :items="TAX_CODE"
          v-model="taxCodeSelected"
          box
          label="Tax Code"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md3>
        <v-select
          :items="NEIGHBORHOOD"
          v-model="neighborhoodSelected"
          box
          label="Neighborhood"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md2>
      
<v-select
          :items="HOUSENO"
          v-model="houseNumber"
          box
          label="House"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>

      <v-flex xs12 sm4 md2>
        <v-select
          :items="DIR"
          v-model="directionSelected"
          box
          label="Direction"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md3>
        <v-select
          :items="STREET"
          v-model="streetSelected"
          box
          label="Street"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md2>
        <v-select
          :items="SUFFIX"
          v-model="suffixSelected"
          box
          label="Suffix"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md2>
        <v-select
          :items="APT"
          v-model="aptSelected"
          box
          label="APT"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md2>
        <v-select
          :items="CITY"
          v-model="citySelected"
          box
          label="City"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md3>
        <v-select
          :items="RES_TYPE"
          v-model="resTypeSelected"
          box
          label="Res Type"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md3>
        <v-select
          :items="BLDG_USE"
          v-model="buildingUseSelected"
          box
          label="Building Use"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md2>
        <v-select
          :items="APT_DESC"
          v-model="aptDescSelected"
          box
          label="Apt Desc"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md2>
        <v-select
          :items="COMM_UNITS"
          v-model="commUnitsSelected"
          box
          label="Comm Units"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md4>
        <v-select
          :items="EXT_DESC"
          v-model="extDescSelected"
          box
          label="Ext Desc"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md2>
        <v-select
          :items="FULL_BATH"
          v-model="fullBathSelected"
          box
          label="Full Bath"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md2>
        <v-select
          :items="HALF_BATH"
          v-model="halfBathSelected"
          box
          label="Half Bath"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md4>
        <v-select
          :items="BSMT_DESC"
          v-model="bsmtDescSelected"
          box
          label="BSMT Desc"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md4>
        <v-select
          :items="ATTIC_DESC"
          v-model="atticDescSelected"
          box
          label="Attic Desc"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm4 md2>
        <v-select
          :items="AC"
          v-model="acSelected"
          box
          label="AC"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md2>
        <v-select
          :items="FIREPLACE"
          v-model="fireplaceSelected"
          box
          label="Fireplace"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md4>
        <v-select
          :items="GAR_DESC"
          v-model="garDescSelected"
          box
          label="Garage Desc"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md4>


 <v-select
          :items="AGE"
          v-model="minAge"
          box
          label="Min Age"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>
      <v-flex xs12 sm6 md4>


 <v-select
          :items="AGE"
          v-model="maxAge"
          box
          label="Max Age"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

       
      </v-flex>

      <v-flex xs12 sm6 md3>

 <v-select
          :items="BUILDING_SQ_FT"
          v-model="minBuildingSqFt"
          box
          label="Min Building Sq Ft"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>
      <v-flex xs12 sm6 md3>



<v-select
          :items="BUILDING_SQ_FT"
          v-model="maxBuildingSqFt"
          box
          label="Max Building Sq Ft"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      
      </v-flex>

      <v-flex xs12 sm6 md3>


<v-select
          :items="LAND_SQ_FT"
          v-model="minLandSqFt"
          box
          label="Min Land Sq Ft"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>
      <v-flex xs12 sm6 md3>


<v-select
          :items="LAND_SQ_FT"
          v-model="maxLandSqFt"
          box
          label="Max Land Sq Ft"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

       
      </v-flex>

      <v-flex xs12 sm6 md3>

<v-select
          :items="BLDG_SF"
          v-model="minBuildingSf"
          box
          label="Min Building SF"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>
      
      <v-flex xs12 sm6 md3>


<v-select
          :items="BLDG_SF"
          v-model="maxBuildingSf"
          box
          label="Max Building SF"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>

      <v-flex xs12 sm6 md3>


<v-select
          :items="UNITS_TOT"
          v-model="minUnitsTotal"
          box
          label="Min Units Total"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
        
      </v-flex>
      <v-flex xs12 sm6 md3>


<v-select
          :items="UNITS_TOT"
          v-model="maxUnitsTotal"
          box
          label="Max Units Total"
          color="success"
          class="ml-1 mr-1"
        ></v-select>



       
      </v-flex>

      <v-flex xs12 sm6 md2>
        <v-select
          :items="MULTI_SALE"
          v-model="multiSaleSelected"
          box
          label="Multi Sale"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md2>
        <v-select
          :items="DEED_TYPE"
          v-model="deedTypeSelected"
          box
          label="Deed Type"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md3>

   <v-select
          :items="SALE_DATE"
          v-model="minSaleDate"
          box
          label="Min Sale Date xx/xx/xxxx"
          color="success"
          class="ml-1 mr-1"
        ></v-select>



      </v-flex>

      <v-flex xs12 sm6 md3>


<v-select
          :items="SALE_DATE"
          v-model="maxSaleDate"
          box
          label="Max Sale Date xx/xx/xxxx"
          color="success"
          class="ml-1 mr-1"
        ></v-select>


      </v-flex>

      <v-flex xs12 sm6 md2>
        <v-select
          :items="APPCNT"
          v-model="appcntSelected"
          box
          label="APPCNT"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md3>

    <v-select
          :items="SALE_AMOUNT"
          v-model="minSaleAmount"
          box
          label="Min Sale Amount"
          color="success"
          class="ml-1 mr-1"
        ></v-select>


      
      </v-flex>
      <v-flex xs12 sm6 md3>
         <v-select
          :items="SALE_AMOUNT"
          v-model="maxSaleAmount"
          box
          label="Max Sale Amount"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md3>

      <v-select
          :items="APPEAL_A"
          v-model="minAppealA"
          box
          label="Min Appeal_A"
          color="success"
          class="ml-1 mr-1"
        ></v-select>


      </v-flex>
      <v-flex xs12 sm6 md3>
     <v-select
          :items="APPEAL_A"
          v-model="maxAppealA"
          box
          label="Max Appeal_A"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>

      <v-flex xs12 sm6 md4>
        <v-select
          :items="APPEAL_A_STATUS"
          v-model="appealAStatusSelected"
          box
          label="Appeal A Status"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md4>
        <v-select
          :items="APPEAL_A_RESULT"
          v-model="appealAResultSelected"
          box
          label="Appeal A Result"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md4>
        <v-select
          :items="APPEAL_A_REASON"
          v-model="appealAReasonSelected"
          box
          label="Appeal A Reason"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md4>
        <v-select
          :items="APPEAL_A_PIN_RESULT"
          v-model="appealAPinResultSelected"
          box
          label="Appeal A Pin Result"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md4>

<v-select
          :items="APPEAL_A_PROPAV"
          v-model="minAppealAPropav"
          box
          label="Min Appeal_A_Propav"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

    
      </v-flex>
      <v-flex xs12 sm6 md4>

<v-select
          :items="APPEAL_A_PROPAV"
          v-model="maxAppealAPropav"
          box
          label="Max Appeal_A_Propav"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>

      <v-flex xs12 sm6 md3>

<v-select
          :items="APPEAL_A_CURRAV"
          v-model="minAppealACurrav"
          box
          label="Min Appeal_A_Currav"
          color="success"
          class="ml-1 mr-1"
        ></v-select>

      </v-flex>
      <v-flex xs12 sm6 md3>
     <v-select
          :items="APPEAL_A_CURRAV"
          v-model="maxAppealACurrav"
          box
          label="Max Appeal_A_Currav"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>

      <v-flex xs12 sm6 md3>

    <v-select
          :items="APPEAL_A_RESLTDATE"
          v-model="minAppealAResultDate"
          box
          label="Min Appeal A Result Date xx/xx/xxxx"
          color="success"
          class="ml-1 mr-1"
        ></v-select>


      </v-flex>

      <v-flex xs12 sm6 md3>
         <v-select
          :items="APPEAL_A_RESLTDATE"
          v-model="maxAppealAResultDate"
          box
          label="Max Appeal A Result Date xx/xx/xxxx"
          color="success"
          class="ml-1 mr-1"
        ></v-select>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script >
// const markersData = require("../AddressInfo");
const markersData = require("../data.js");




export default {
  data() {
    return {
      previousMarker: null,
      markers: markersData.markers,
      allMarkers: [],
      fulladdress: [],
      LatitudeonLoad: [],
      LongLoad: [],
      zipitm: [],
      ESTIMATED_MARKET_VALUE:[],
      minCurrent_Building: [],
      Min_Current_Total:[],
      PRIOR_LAND:[],
    
PRIOR_BUILDING: [],
PRIOR_TOTAL:[],
PPRIOR_LAND:[],
PPRIOR_BUILDING: [],
PPRIOR_TOTAL:[],
PPRIOR_YEAR: [],
TOWN:[],
VOLUME:[],
LOC:[],
TAX_CODE:[],
NEIGHBORHOOD:[],
HOUSENO:[],
DIR:[],
STREET: [],
SUFFIX: [],
APT: [],
CITY:[],
RES_TYPE:[],
BLDG_USE:[],
APT_DESC:[],
EXT_DESC:[],
COMM_UNITS:[],
FULL_BATH:[],
HALF_BATH:[],
BSMT_DESC:[],
ATTIC_DESC:[],
AC:[],
FIREPLACE:[],
GAR_DESC:[],
AGE:[],
BUILDING_SQ_FT:[],
LAND_SQ_FT:[],
BLDG_SF:[],
UNITS_TOT:[],
MULTI_SALE:[],
DEED_TYPE:[],
SALE_DATE:[],
SALE_AMOUNT:[],
APPCNT:[],
APPEAL_A:[],
APPEAL_A_STATUS:[],
APPEAL_A_RESULT:[],
APPEAL_A_REASON:[],
APPEAL_A_PIN_RESULT:[],
APPEAL_A_PROPAV:[],
APPEAL_A_CURRAV:[],
APPEAL_A_RESLTDATE:[],

      Pincode: [],
      minCurrent_Land: [],
      class_descriptionItems: [],
      full_address: "",
      latitude: "",
      longitude: "",
      zipSelected: "",
      recItems: ["Any", "A-HD"],
      recSelected: "",
      pin: "",
      OVACLScode: [],
      ovaclsSelected: "",
      class_descriptionSelected: "",
      minCurrentLand: "",
      maxCurrentLand: "",
      minCurrentBuilding: "",
      maxCurrentBuilding: "",
      minCurrentTotal: "",
      maxCurrentTotal: "",
      minEstimatedMarketValue: "",
      maxEstimatedMarketValue: "",
      minPriorLand: "",
      maxPriorLand: "",
      minPriorBuilding: "",
      maxPriorBuilding: "",
      minPriorTotal: "",
      maxPriorTotal: "",
      minPPriorLand: "",
      maxPPriorLand: "",
      minPPriorBuilding: "",
      maxPPriorBuilding: "",
      minPPriorTotal: "",
      maxPPriorTotal: "",
      minPPriorYear: "",
      maxPPriorYear: "",
      townSelected: "",
      
      volumeSelected: "",
      
      locSelected: "",
      
      taxCodeSelected: "",
      
      neighborhoodSelected: "",
      houseNumber: "",
      directionSelected: "",
     
      streetSelected: "",
     
      suffixSelected: "",
      
      aptSelected: "",
     
      citySelected: "",
    
      resTypeSelected: "",
     
      buildingUseSelected: "",
      
      aptDescSelected: "",
     
      commUnitsSelected: "",
   
      extDescSelected: "",
      
      fullBathSelected: "",

      halfBathSelected: "",
     
      bsmtDescSelected: "",
    
      atticDescSelected: "",
      
      acSelected: "",
      
      fireplaceSelected: "",
    
      garDescSelected: "",
      minAge: "",
      maxAge: "",
      minBuildingSqFt: "",
      maxBuildingSqFt: "",
      minLandSqFt: "",
      maxLandSqFt: "",
      minBuildingSf: "",
      maxBuildingSf: "",
      minUnitsTotal: "",
      maxUnitsTotal: "",
      multiSaleSelected: "",
     
      deedTypeSelected: "",
      minSaleDate: "",
      maxSaleDate: "",
      minSaleAmount: "",
      maxSaleAmount: "",
      
      appcntSelected: "",
      minAppealA: "",
      maxAppealA: "",
    
      appealAStatusSelected: "",
     
      appealAResultSelected: "",
   
      appealAReasonSelected: "",
  
      appealAPinResultSelected: "",
      minAppealAPropav: "",
      maxAppealAPropav: "",
      minAppealACurrav: "",
      maxAppealACurrav: "",
      minAppealAResultDate: "",
      maxAppealAResultDate: ""
    };
  },
  mounted() {
    this.markers.forEach((data) => {
        this.fulladdress.push(data.properties.Full_Address);
        this.LatitudeonLoad.push(data.coords.lat);
        this.LongLoad.push(data.coords.lng);
        this.Pincode.push(data.properties.PIN);
        this.zipitm.push(data.properties.Zip);
        this.OVACLScode.push(data.properties.OVACLS);
        this.class_descriptionItems.push(data.properties.CLASS_DESCRIPTION);
        this.minCurrent_Land.push(data.properties.CURRENT_LAND);
        this.minCurrent_Building.push(data.properties.CURRENT_BUILDING);
        this.Min_Current_Total.push(data.properties.CURRENT_TOTAL);

        this.ESTIMATED_MARKET_VALUE.push(data.properties.ESTIMATED_MARKET_VALUE);
        this.PRIOR_LAND.push(data.properties.PRIOR_LAND);
 this.PRIOR_BUILDING.push(data.properties.PRIOR_BUILDING);
  this.PRIOR_TOTAL.push(data.properties.PRIOR_TOTAL);
   this.PPRIOR_LAND.push(data.properties.PPRIOR_LAND);
   this.PPRIOR_BUILDING.push(data.properties.PPRIOR_BUILDING);
    this.PPRIOR_TOTAL.push(data.properties.PPRIOR_TOTAL);
     this.PPRIOR_YEAR.push(data.properties.PPRIOR_YEAR);
      this.TOWN.push(data.properties.TOWN);
       this.VOLUME.push(data.properties.VOLUME);
        this.LOC.push(data.properties.LOC);
         this.TAX_CODE.push(data.properties.TAX_CODE);
          this.NEIGHBORHOOD.push(data.properties.NEIGHBORHOOD);
           this.HOUSENO.push(data.properties.HOUSENO);
            this.DIR.push(data.properties.DIR);
             this.STREET.push(data.properties.STREET);
              this.SUFFIX.push(data.properties.SUFFIX);
        this.APT.push(data.properties.APT);
        this.CITY.push(data.properties.CITY);

          this.RES_TYPE.push(data.properties.RES_TYPE);
            this.BLDG_USE.push(data.properties.BLDG_USE);
              this.APT_DESC.push(data.properties.APT_DESC);
              this.COMM_UNITS.push(data.properties.COMM_UNITS);
              this.APT_DESC.push(data.properties.APT_DESC);
                this.EXT_DESC.push(data.properties.EXT_DESC);
                  this.FULL_BATH.push(data.properties.FULL_BATH);
                    this.HALF_BATH.push(data.properties.HALF_BATH);
                      this.BSMT_DESC.push(data.properties.BSMT_DESC);
                        this.ATTIC_DESC.push(data.properties.ATTIC_DESC);
                          this.AC.push(data.properties.AC);
                            this.FIREPLACE.push(data.properties.FIREPLACE);

                             this.GAR_DESC.push(data.properties.GAR_DESC);
                              this.AGE.push(data.properties.AGE);
                               this.BUILDING_SQ_FT.push(data.properties.BUILDING_SQ_FT);
                                this.LAND_SQ_FT.push(data.properties.LAND_SQ_FT);
                                 this.BLDG_SF.push(data.properties.BLDG_SF);
                                  this.UNITS_TOT.push(data.properties.UNITS_TOT);
                                   this.MULTI_SALE.push(data.properties.MULTI_SALE);
                                    this.DEED_TYPE.push(data.properties.DEED_TYPE);
                                     this.SALE_DATE.push(data.properties.SALE_DATE);
                                     this.SALE_AMOUNT.push(data.properties.SALE_AMOUNT);
                                     this.APPCNT.push(data.properties.APPCNT);
                                     this.APPEAL_A.push(data.properties.APPEAL_A);
                                     this.APPEAL_A_STATUS.push(data.properties.APPEAL_A_STATUS);
                                     this.APPEAL_A_RESULT.push(data.properties.APPEAL_A_RESULT);
                                     this.APPEAL_A_REASON.push(data.properties.APPEAL_A_REASON);
                                     this.APPEAL_A_PIN_RESULT.push(data.properties.APPEAL_A_PIN_RESULT);
                                     this.APPEAL_A_PROPAV.push(data.properties.APPEAL_A_PROPAV);
                                     this.APPEAL_A_CURRAV.push(data.properties.APPEAL_A_CURRAV);
                                     this.APPEAL_A_RESLTDATE.push(data.properties.APPEAL_A_RESLTDATE);

        
  

    });
    // console.log(this.markers[0]);
    this.initMap();

  },
  methods: {
    applyFilters() {
      this.markers.forEach((address, i) => {
        //Start with all markers visible
        this.allMarkers[i].setVisible(true);

        // Check Full Address
        if (this.full_address != "") {
          if (
            address.properties.Full_Address.toLowerCase().includes(
              this.full_address.toLowerCase()
            ) == false
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Zipcode
        if (this.zipSelected != "" && this.zipSelected != "Any") {
          if (address.properties.Zip != this.zipSelected) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Latitude
        if (this.latitude != "") {
          let strToFloat = parseFloat(this.latitude);

          let difference = Math.abs(strToFloat - address.coords.lat);

          // console.log(difference > 0.01);

          if (difference > 0.01 == true) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Longitude
        if (this.longitude != "") {
          let strToFloatLon = parseFloat(this.longitude);

          let difference = Math.abs(strToFloatLon - address.coords.lng);

          // console.log(difference > 0.01);

          if (difference > 0.01 == true) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Rec_Type
        if (this.recSelected != "" && this.recSelected != "Any") {
          if (address.properties.REC_TYPE != this.recSelected) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Pin
        if (this.pin != "") {
          if (
            address.properties.PIN.toLowerCase().includes(
              this.pin.toLowerCase()
            ) == false
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check OVACLS
        if (this.ovaclsSelected != "" && this.ovaclsSelected != "Any") {
          if (address.properties.OVACLS != this.ovaclsSelected) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check CLASS_DESCRIPTION
        if (
          this.class_descriptionSelected != "" &&
          this.class_descriptionSelected != "Any"
        ) {
          if (
            address.properties.CLASS_DESCRIPTION !=
            this.class_descriptionSelected
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min Current Land
        if (this.minCurrentLand != "") {
          if (
            address.properties.CURRENT_LAND <
            parseInt(this.minCurrentLand.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max Current Land
        if (this.maxCurrentLand != "") {
          if (
            address.properties.CURRENT_LAND >
            parseInt(this.maxCurrentLand.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min Current Building
        if (this.minCurrentBuilding != "") {
          if (
            address.properties.CURRENT_BUILDING <
            parseInt(this.minCurrentBuilding.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max Current Building
        if (this.maxCurrentBuilding != "") {
          if (
            address.properties.CURRENT_BUILDING >
            parseInt(this.maxCurrentBuilding.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min Current Total
        if (this.minCurrentTotal != "") {
          if (
            address.properties.CURRENT_TOTAL <
            parseInt(this.minCurrentTotal.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max Current Total
        if (this.maxCurrentTotal != "") {
          if (
            address.properties.CURRENT_TOTAL >
            parseInt(this.maxCurrentTotal.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min Est Market Value
        if (this.minEstimatedMarketValue != "") {
          if (
            address.properties.ESTIMATED_MARKET_VALUE <
            parseInt(this.minEstimatedMarketValue.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max Est Market Value
        if (this.maxEstimatedMarketValue != "") {
          if (
            address.properties.ESTIMATED_MARKET_VALUE >
            parseInt(this.maxEstimatedMarketValue.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min Prior Land
        if (this.minPriorLand != "") {
          if (
            address.properties.PRIOR_LAND <
            parseInt(this.minPriorLand.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max Prior Land
        if (this.maxPriorLand != "") {
          if (
            address.properties.PRIOR_LAND >
            parseInt(this.maxPriorLand.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min Prior Building
        if (this.minPriorBuilding != "") {
          if (
            address.properties.PRIOR_BUILDING <
            parseInt(this.minPriorBuilding.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max Prior Building
        if (this.maxPriorBuilding != "") {
          if (
            address.properties.PRIOR_BUILDING >
            parseInt(this.maxPriorBuilding.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min Prior Total
        if (this.minPriorTotal != "") {
          if (
            address.properties.PRIOR_TOTAL <
            parseInt(this.minPriorTotal.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max Prior Total
        if (this.maxPriorTotal != "") {
          if (
            address.properties.PRIOR_TOTAL >
            parseInt(this.maxPriorTotal.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min PPrior Land
        if (this.minPPriorLand != "") {
          if (
            address.properties.PPRIOR_LAND <
            parseInt(this.minPPriorLand.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max PPrior Land
        if (this.maxPPriorLand != "") {
          if (
            address.properties.PPRIOR_LAND >
            parseInt(this.maxPPriorLand.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min PPrior Building
        if (this.minPPriorBuilding != "") {
          if (
            address.properties.PPRIOR_BUILDING <
            parseInt(this.minPPriorBuilding.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max PPrior Building
        if (this.maxPPriorBuilding != "") {
          if (
            address.properties.PPRIOR_BUILDING >
            parseInt(this.maxPPriorBuilding.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min PPrior Total
        if (this.minPPriorTotal != "") {
          if (
            address.properties.PPRIOR_TOTAL <
            parseInt(this.minPPriorTotal.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max PPrior Total
        if (this.maxPPriorTotal != "") {
          if (
            address.properties.PPRIOR_TOTAL >
            parseInt(this.maxPPriorTotal.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min PPrior Year
        if (this.minPPriorYear != "") {
          if (
            parseInt(address.properties.PPRIOR_YEAR) <
            parseInt(this.minPPriorYear)
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max PPrior Year
        if (this.maxPPriorYear != "") {
          if (
            parseInt(address.properties.PPRIOR_YEAR) >
            parseInt(this.maxPPriorYear)
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check TOWN
        if (this.townSelected != "" && this.townSelected != "Any") {
          if (address.properties.TOWN != this.townSelected) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Volume
        if (this.volumeSelected != "" && this.volumeSelected != "Any") {
          if (address.properties.VOLUME != this.volumeSelected) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Loc
        if (this.locSelected != "" && this.locSelected != "Any") {
          if (address.properties.LOC != this.locSelected) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Tax Code
        if (this.taxCodeSelected != "" && this.taxCodeSelected != "Any") {
          if (address.properties.TAX_CODE != this.taxCodeSelected) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Neighborhood
        if (
          this.neighborhoodSelected != "" &&
          this.neighborhoodSelected != "Any"
        ) {
          if (address.properties.NEIGHBORHOOD != this.neighborhoodSelected) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check House Number
        if (this.houseNumber != "") {
          if (
            address.properties.HOUSENO.toLowerCase().includes(
              this.houseNumber.toLowerCase()
            ) == false
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Dir
        if (this.directionSelected != "" && this.directionSelected != "Any") {
          if (address.properties.DIR != this.directionSelected) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Street
        if (this.streetSelected != "" && this.streetSelected != "Any") {
          if (
            address.properties.STREET.toLowerCase() !=
            this.streetSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check SUFFIX
        if (this.suffixSelected != "" && this.suffixSelected != "Any") {
          if (
            address.properties.SUFFIX.toLowerCase() !=
            this.suffixSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check APT
        if (this.aptSelected != "" && this.aptSelected != "Any") {
          if (
            address.properties.APT.toLowerCase() !=
            this.aptSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check City
        if (this.citySelected != "" && this.citySelected != "Any") {
          if (
            address.properties.CITY.toLowerCase() !=
            this.citySelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Res_TYPE
        if (this.resTypeSelected != "" && this.resTypeSelected != "Any") {
          if (
            address.properties.RES_TYPE.toLowerCase() !=
            this.resTypeSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check BLDG_USE
        if (
          this.buildingUseSelected != "" &&
          this.buildingUseSelected != "Any"
        ) {
          if (
            address.properties.BLDG_USE.toLowerCase() !=
            this.buildingUseSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check APT_DESC
        if (this.aptDescSelected != "" && this.aptDescSelected != "Any") {
          if (
            address.properties.APT_DESC.toLowerCase() !=
            this.aptDescSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check COMM_UNITS
        if (this.commUnitsSelected != "" && this.commUnitsSelected != "Any") {
          if (
            address.properties.COMM_UNITS.toLowerCase() !=
            this.commUnitsSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check EXT_DESC
        if (this.extDescSelected != "" && this.extDescSelected != "Any") {
          if (
            address.properties.EXT_DESC.toLowerCase() !=
            this.extDescSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check FULL_BATH
        if (this.fullBathSelected != "" && this.fullBathSelected != "Any") {
          if (
            address.properties.FULL_BATH.toLowerCase() !=
            this.fullBathSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check HALF_BATH
        if (this.halfBathSelected != "" && this.halfBathSelected != "Any") {
          if (
            address.properties.HALF_BATH.toLowerCase() !=
            this.halfBathSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check BSMT_DESC
        if (this.bsmtDescSelected != "" && this.bsmtDescSelected != "Any") {
          if (
            address.properties.BSMT_DESC.toLowerCase() !=
            this.bsmtDescSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check ATTIC_DESC
        if (this.atticDescSelected != "" && this.atticDescSelected != "Any") {
          if (
            address.properties.ATTIC_DESC.toLowerCase() !=
            this.atticDescSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check AC
        if (this.acSelected != "" && this.acSelected != "Any") {
          if (
            address.properties.AC.toLowerCase() != this.acSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check FIREPLACE
        if (this.fireplaceSelected != "" && this.fireplaceSelected != "Any") {
          if (
            address.properties.FIREPLACE.toLowerCase() !=
            this.fireplaceSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check GAR_DESC
        if (this.garDescSelected != "" && this.garDescSelected != "Any") {
          if (
            address.properties.GAR_DESC.toLowerCase() !=
            this.garDescSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min Age_
        if (this.minAge != "") {
          if (parseInt(address.properties.AGE) < parseInt(this.minAge)) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max Age_
        if (this.maxAge != "") {
          if (parseInt(address.properties.AGE) > parseInt(this.maxAge)) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min BUILDING_SQ_FT
        if (this.minBuildingSqFt != "") {
          if (
            parseInt(address.properties.BUILDING_SQ_FT) <
            parseInt(this.minBuildingSqFt.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max BUILDING_SQ_FT
        if (this.maxBuildingSqFt != "") {
          if (
            parseInt(address.properties.BUILDING_SQ_FT) >
            parseInt(this.maxBuildingSqFt.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min LAND_SQ_FT
        if (this.minLandSqFt != "") {
          if (
            parseInt(address.properties.LAND_SQ_FT) <
            parseInt(this.minLandSqFt.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max LAND_SQ_FT
        if (this.maxLandSqFt != "") {
          if (
            parseInt(address.properties.LAND_SQ_FT) >
            parseInt(this.maxLandSqFt.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min BLDG_SF
        if (this.minBuildingSf != "") {
          if (
            parseInt(address.properties.BLDG_SF) <
            parseInt(this.minBuildingSf.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max BLDG_SF
        if (this.maxBuildingSf != "") {
          if (
            parseInt(address.properties.BLDG_SF) >
            parseInt(this.maxBuildingSf.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min UNITS_TOT
        if (this.minUnitsTotal != "") {
          if (
            parseInt(address.properties.UNITS_TOT) <
            parseInt(this.minUnitsTotal.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max UNITS_TOT
        if (this.maxUnitsTotal != "") {
          if (
            parseInt(address.properties.UNITS_TOT) >
            parseInt(this.maxUnitsTotal.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check MULTI_SALE
        if (this.multiSaleSelected != "" && this.multiSaleSelected != "Any") {
          if (
            address.properties.MULTI_SALE.toLowerCase() !=
            this.multiSaleSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check DEED_TYPE
        if (this.deedTypeSelected != "" && this.deedTypeSelected != "Any") {
          if (
            address.properties.DEED_TYPE.toLowerCase() !=
            this.deedTypeSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min SALE_AMOUNT
        if (this.minSaleAmount != "") {
          if (
            parseInt(address.properties.SALE_AMOUNT) <
            parseInt(this.minSaleAmount.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max SALE_AMOUNT
        if (this.maxSaleAmount != "") {
          if (
            parseInt(address.properties.SALE_AMOUNT) >
            parseInt(this.maxSaleAmount.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check APPCNT
        if (this.appcntSelected != "" && this.appcntSelected != "Any") {
          if (
            address.properties.APPCNT.toLowerCase() !=
            this.appcntSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min APPEAL_A
        if (this.minAppealA != "") {
          if (
            parseInt(address.properties.APPEAL_A) <
            parseInt(this.minAppealA.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max APPEAL_A
        if (this.maxAppealA != "") {
          if (
            parseInt(address.properties.APPEAL_A) >
            parseInt(this.maxAppealA.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check APPEAL_A_STATUS
        if (
          this.appealAStatusSelected != "" &&
          this.appealAStatusSelected != "Any"
        ) {
          if (
            address.properties.APPEAL_A_STATUS.toLowerCase() !=
            this.appealAStatusSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check APPEAL_A_RESULT
        if (
          this.appealAResultSelected != "" &&
          this.appealAResultSelected != "Any"
        ) {
          if (
            address.properties.APPEAL_A_RESULT.toLowerCase() !=
            this.appealAResultSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check APPEAL_A_REASON
        if (
          this.appealAReasonSelected != "" &&
          this.appealAReasonSelected != "Any"
        ) {
          if (
            address.properties.APPEAL_A_REASON.toLowerCase() !=
            this.appealAReasonSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check APPEAL_A_PIN_RESULT
        if (
          this.appealAPinResultSelected != "" &&
          this.appealAPinResultSelected != "Any"
        ) {
          if (
            address.properties.APPEAL_A_PIN_RESULT.toLowerCase() !=
            this.appealAPinResultSelected.toLowerCase()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min APPEAL_A_PROPAV
        if (this.minAppealAPropav != "") {
          if (
            parseInt(address.properties.APPEAL_A_PROPAV) <
            parseInt(this.minAppealAPropav.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max APPEAL_A_PROPAV
        if (this.maxAppealAPropav != "") {
          if (
            parseInt(address.properties.APPEAL_A_PROPAV) >
            parseInt(this.maxAppealAPropav.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min APPEAL_A_CURRAV
        if (this.minAppealACurrav != "") {
          if (
            parseInt(address.properties.APPEAL_A_CURRAV) <
            parseInt(this.minAppealACurrav.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max APPEAL_A_CURRAV
        if (this.maxAppealACurrav != "") {
          if (
            parseInt(address.properties.APPEAL_A_CURRAV) >
            parseInt(this.maxAppealACurrav.replace(/,/g, ""))
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min SALE_DATE
        if (this.minSaleDate != "") {
          let splitString = this.minSaleDate.split("/");

          if (parseInt(splitString[2]) < 22) {
            splitString[2] = "20" + splitString[2];
          } else if (
            parseInt(splitString[2]) > 22 &&
            parseInt(splitString[2]) < 1000
          ) {
            splitString[2] = "19" + splitString[2];
          }

          let newString =
            splitString[2] + "/" + splitString[0] + "/" + splitString[1];

          let dateObject = new Date(newString);

          let dateObjectFromAddress = new Date(address.properties.SALE_DATE);

          if (
            dateObjectFromAddress.getTime() <
            dateObject.getTime()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max SALE_DATE
        if (this.maxSaleDate != "") {
          let splitString = this.maxSaleDate.split("/");

          if (parseInt(splitString[2]) < 22) {
            splitString[2] = "20" + splitString[2];
          } else if (
            parseInt(splitString[2]) > 22 &&
            parseInt(splitString[2]) < 1000
          ) {
            splitString[2] = "19" + splitString[2];
          }

          let newString =
            splitString[2] + "/" + splitString[0] + "/" + splitString[1];

          let dateObject = new Date(newString);

          let dateObjectFromAddress = new Date(address.properties.SALE_DATE);

          if (
            dateObjectFromAddress.getTime() >
            dateObject.getTime()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Min APPEAL_A_RESLTDATE
        if (this.minAppealAResultDate != "") {
          let splitString = this.minAppealAResultDate.split("/");

          if (parseInt(splitString[2]) < 22) {
            splitString[2] = "20" + splitString[2];
          } else if (
            parseInt(splitString[2]) > 22 &&
            parseInt(splitString[2]) < 1000
          ) {
            splitString[2] = "19" + splitString[2];
          }

          let newString =
            splitString[2] + "/" + splitString[0] + "/" + splitString[1];

          let dateObject = new Date(newString);

          let dateObjectFromAddress = new Date(address.properties.APPEAL_A_RESLTDATE);

          if (
            dateObjectFromAddress.getTime() <
            dateObject.getTime()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // Check Max APPEAL_A_RESLTDATE
        if (this.maxAppealAResultDate != "") {
          let splitString = this.maxAppealAResultDate.split("/");

          if (parseInt(splitString[2]) < 22) {
            splitString[2] = "20" + splitString[2];
          } else if (
            parseInt(splitString[2]) > 22 &&
            parseInt(splitString[2]) < 1000
          ) {
            splitString[2] = "19" + splitString[2];
          }

          let newString =
            splitString[2] + "/" + splitString[0] + "/" + splitString[1];

          let dateObject = new Date(newString);

          let dateObjectFromAddress = new Date(address.properties.APPEAL_A_RESLTDATE);

          if (
            dateObjectFromAddress.getTime() >
            dateObject.getTime()
          ) {
            this.allMarkers[i].setVisible(false);
            // Close info window if last selected becomes hidden
            if (this.previousMarker == this.allMarkers[i]) {
              this.previousMarker.infowindow.close();
            }
          }
        }

        // End of Filter function
      });
    },
    clearFilters() {
      this.full_address = "";
      this.latitude = "";
      this.longitude = "";
      this.zipSelected = "";
      this.recSelected = "";
      this.pin = "";
      this.ovaclsSelected = "";
      this.class_descriptionSelected = "";
      this.minCurrentLand = "";
      this.maxCurrentLand = "";
      this.minCurrentBuilding = "";
      this.maxCurrentBuilding = "";
      this.minCurrentTotal = "";
      this.maxCurrentTotal = "";
      this.minEstimatedMarketValue = "";
      this.maxEstimatedMarketValue = "";
      this.minPriorLand = "";
      this.maxPriorLand = "";
      this.minPriorBuilding = "";
      this.maxPriorBuilding = "";
      this.minPriorTotal = "";
      this.maxPriorTotal = "";
      this.minPPriorLand = "";
      this.maxPPriorLand = "";
      this.minPPriorBuilding = "";
      this.maxPPriorBuilding = "";
      this.minPPriorTotal = "";
      this.maxPPriorTotal = "";
      this.minPPriorYear = "";
      this.maxPPriorYear = "";
      this.townSelected = "";
      this.volumeSelected = "";
      this.locSelected = "";
      this.taxCodeSelected = "";
      this.neighborhoodSelected = "";
      this.houseNumber = "";
      this.directionSelected = "";
      this.streetSelected = "";
      this.suffixSelected = "";
      this.aptSelected = "";
      this.citySelected = "";
      this.resTypeSelected = "";
      this.buildingUseSelected = "";
      this.aptDescSelected = "";
      this.commUnitsSelected = "";
      this.extDescSelected = "";
      this.fullBathSelected = "";
      this.halfBathSelected = "";
      this.bsmtDescSelected = "";
      this.atticDescSelected = "";
      this.acSelected = "";
      this.fireplaceSelected = "";
      this.garDescSelected = "";
      this.minAge = "";
      this.maxAge = "";
      this.minBuildingSqFt = "";
      this.maxBuildingSqFt = "";
      this.minLandSqFt = "";
      this.maxLandSqFt = "";
      this.minBuildingSf = "";
      this.maxBuildingSf = "";
      this.minUnitsTotal = "";
      this.maxUnitsTotal = "";
      this.multiSaleSelected = "";
      this.deedTypeSelected = "";
      this.minSaleDate = "";
      this.maxSaleDate = "";
      this.minSaleAmount = "";
      this.maxSaleAmount = "";
      this.appcntSelected = "";
      this.minAppealA = "";
      this.maxAppealA = "";
      this.appealAStatusSelected = "";
      this.appealAResultSelected = "";
      this.appealAReasonSelected = "";
      this.appealAPinResultSelected = "";
      this.minAppealAPropav = "";
      this.maxAppealAPropav = "";
      this.minAppealACurrav = "";
      this.maxAppealACurrav = "";
      this.minAppealAResultDate = "";
      this.maxAppealAResultDate = "";
      this.allMarkers.forEach(address => {
        address.setVisible(true);
      });
    },
    current_land_filter(value) {
      console.log(value);
    },
    showAll() {
      this.allMarkers.forEach(address => {
        address.setVisible(true);
      });
    },
    removeTwoBathrooms() {
      this.markers.forEach((address, i) => {
        if (address.properties.bathrooms == 2) {
          this.allMarkers[i].setVisible(false);
          if (this.previousMarker == this.allMarkers[i]) {
            this.previousMarker.infowindow.close();
          }
        }
      });
    },
    initMap() {
      // Map options
      var options = {
        zoom: 12,
        center: { lat: 41.9, lng: -87.6676657 }
      };
      // New Map
      var map = new google.maps.Map(document.getElementById("map"), options);

      // Loops through markers
      this.markers.forEach(address => {
        var marker = new google.maps.Marker({
          position: address.coords,
          map: map,
          visible: address.visible
        });

        // Add markers with colors

        if (address.properties.ESTIMATED_MARKET_VALUE <= 400000) {
          marker.setIcon(
            "https://maps.google.com/mapfiles/ms/icons/red-dot.png"
          );
        }

        if (
          address.properties.ESTIMATED_MARKET_VALUE > 400000 &&
          address.properties.ESTIMATED_MARKET_VALUE <= 450000
        ) {
          marker.setIcon(
            "https://maps.google.com/mapfiles/ms/icons/orange-dot.png"
          );
        }

        if (
          address.properties.ESTIMATED_MARKET_VALUE > 450000 &&
          address.properties.ESTIMATED_MARKET_VALUE <= 525000
        ) {
          marker.setIcon(
            "https://maps.google.com/mapfiles/ms/icons/yellow-dot.png"
          );
        }

        if (address.properties.ESTIMATED_MARKET_VALUE > 525001) {
          marker.setIcon(
            "https://maps.google.com/mapfiles/ms/icons/green-dot.png"
          );
        }

        if (address.content) {
          marker.infowindow = new google.maps.InfoWindow({
            content: address.content
          });
          marker.addListener("mouseover", () => {
            marker.infowindow.open(map, marker);
            if (this.previousMarker) {
              this.previousMarker.infowindow.close();
              if (this.previousMarker == marker) {
                marker.infowindow.open(map, marker);
              }
            }

            this.previousMarker = marker;
          });
        }
        this.allMarkers.push(marker);
      });
    }
  }
};
</script>

<style>
#map {
  height: 400px;
  width: 100%;
}
</style>
