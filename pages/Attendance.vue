<template>
<div>
   <HomepageImage></HomepageImage>
    <b-link href="/"><button class="back">BACK</button></b-link>
 
    <h1 class="Atitle">BIT ATTENDANCE SCREEN</h1>
     <img src="../assets/Key.PNG" class="key"/>
     <h2 class="Btitle">Paper + Stream</h2>
     <Totals></Totals>
    <MarkAttendance></MarkAttendance>
   
  
  </div>
</template>

<script>
export default {

};
</script>

<style>
.mainContainer {
  max-width: 100%;
}

.back {
  margin-left: 350px;
  margin-top: 15px;
  padding: 10px;
}
.Atitle {
  margin-top: -100px;
  text-align: center;
}
.Btitle{
  text-align: center;
  margin-top: 75px;
  margin-left: 260px;
}
.key{
  float:right;
    margin-top: -50px;
  margin-right: 100px;
  height: 200px;
}

</style>
