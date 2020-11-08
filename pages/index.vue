<template>
  <div class="mainContainer">
    <HomepageImage></HomepageImage>
    <h1 class="title">BIT ATTENDANCE SCREEN</h1>
    <h2 class="selectPaper">SELECT PAPER *</h2>
    <h2 class="selectStream">SELECT STREAM *</h2>
    <PaperDropDown></PaperDropDown>

    <NuxtLink to="./Attendance">   
     <button class="start">Start</button>
    </NuxtLink>
   

  </div>
</template>

<script>
export default {};
</script>

<style>
.mainContainer {
  position: relative;
  max-width: 100%;
}
.title {
  text-align: center;
  padding-top: 4%;
  z-index: 5;
}

.selectPaper {
  text-align: center;
  padding-top: 5%;
  margin-right: 25%;
}
.selectStream {
  text-align: center;
  padding-top: 3%;
  margin-right: 24%;
}

.start {
  padding: 0.7%;
  width: 10%;
  margin-top: 6%;
  margin-left: 45%;
}

@media only screen and (max-width: 600px) {
  .start {
    margin-top: 40%;
    width: 30%;
  }
}
/*

.title {
  position: absolute;
  margin-top: 120px;
  margin-left: 40%;
  max-width: 100%;
}

.selectPaper {
  position: absolute;
  margin-top: 350px;
  margin-left: 25%;
  max-width: 100%;
}
.selectStream {
  position: absolute;
  margin-top: 450px;
  margin-left: 25%;
  max-width: 100%;
}
.start{
  position: absolute;
  margin-top: 120px;
  margin-left: 40%;
  max-width: 100%;
} */
</style>
