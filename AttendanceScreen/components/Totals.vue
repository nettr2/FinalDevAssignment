<template>
  <div id="Totals">
    <h3 id="dateTotals"></h3>
    <table id="Totals">
      <tr>
        <th>Postitive</th>
        <th>Neutral</th>
        <th>Negative</th>
      </tr>
      <tr>
        <td></td>
        <td></td>
        <td></td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "Totals",
  mounted() {
    // var d = new Date();
    // document.getElementById("dateTotals").innerHTML = d.toDateString();
    
  }
};
</script>

<style>
h3 {
  margin-left: 30px;
}
#Totals {
  font-family: Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  margin-left: 25px;
}

#Totals td,
#Totals th {
  border: 1px solid #ddd;
  padding: 8px;
  width: 125px;
  height: 50px;
}

#Totals th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
}
</style>
