<template>
<div class="main">
<div>


<select name="paper" id="paper" class="paper">
  <option value="selectPaper"> Select Paper </option>
  <option value="db3">IN705 DB3</option>
  <option value="ux">IN729 UX Engineering</option>
  <option value="studio">IN700 Studio 5</option>
   <option value="mobile">IN721 Mobile</option>
</select>


<select name="stream" id="stream" class="stream">
  <option value="selectStream">Select Stream</option>
  <option value="streamA">Stream A</option>
  <option value="streamB">Stream B</option>
</select>

</div>
</div>




</template>

<script>
export default {}
</script>

<style>

.main {
  position: relative;
  max-width: 100%;
}

.paper{
  position: absolute;
  top: -145px;
  margin-left: 48%;
  width: 22%;
  padding: 8px;
  max-width: 100%;
  overflow-wrap: break-word;

}
.stream{
  position: absolute;
  top: -45px;
  margin-left: 48%;
  width: 22%;
  padding: 8px;
  max-width: 100%;
  
}

@media only screen and (max-width: 1351px) and (min-width: 800px) {

.paper{
  top: -145px;
  margin-left: 55%;
}
.stream{

  top: -45px;
  margin-left: 55%; 
}

}

@media only screen and (max-width: 800px) and (min-width: 600px){

.paper{
  top: -128px;
  margin-left:60%;
}
.stream{
  top: -45px;
  margin-left: 60%;
}
}

@media only screen and (max-width: 600px) {

 

.paper{

  top: 20px;
  margin-left:30%;
  width: 200px;
 

}
.stream{
 
 top: 75px;
  margin-left:30%;
  width: 200px;
  

}
}



</style>