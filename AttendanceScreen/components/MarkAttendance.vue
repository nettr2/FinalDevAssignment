<template>
  <div id="attendance">
    <table id="attendance">
      <tr id="header">
        <th>
          <select name="month" id="month" class="month">
            <option value="selectPaper"> Select Month </option>
            <option value="january">January</option>
            <option value="febuary">Febuary</option>
            <option value="march">March</option>
            <option value="april">April</option>
            <option value="may">May</option>
            <option value="june">June</option>
            <option value="july">July</option>
            <option value="augusy">August</option>
            <option value="september">September</option>
            <option value="october">October</option>
            <option value="november">November</option>
            <option value="december">December</option>
          </select>
        </th>
      </tr>
      <tr id="marks0">
        <td id="name0"></td>
      </tr>
      <tr id="marks1">
        <td id="name1"></td>
      </tr>
      <tr id="marks2">
        <td id="name2"></td>
      </tr>

      <tr id="marks3">
        <td id="name3"></td>
      </tr>
      <button id="save">Save Changes</button>
    </table>
  </div>
</template>

<script>
export default {
  name: "MarkAttendance",

  mounted() {
    fetch(
      "https://gist.githubusercontent.com/eallenOP/b40fa9bba517ff258da395c79edd2477/raw/a8175e0b5c915d9e2d857a2f114704094ade22b9"
    )
      .then(response => response.json())
      .then(data => workwithdata(data));

    function workwithdata(data) {
      var i;
      var j;
      window.localStorage.setItem("StoredPersons", JSON.stringify(data));
      let accessedPersons = JSON.parse(
        window.localStorage.getItem("StoredPersons")
      );
      // let results = accessedPersons[0].name.first
      // console.log(results);
      let tableref = document.getElementById("attendance");

      let row = document.getElementById("header");
      let row2 = document.getElementById("marks0");
      let row3 = document.getElementById("marks1");
      let row4 = document.getElementById("marks2");
      let row5 = document.getElementById("marks3");

      for (i = 0; i < 30; i++) {
        let newcell2 = row2.insertCell(i + 1);
        let newcell3 = row3.insertCell(i + 1);
        let newcell4 = row4.insertCell(i + 1);
        let newcell5 = row5.insertCell(i + 1);
        let newcell = row.insertCell(i + 1);
        newcell.setAttribute("id", "date" + i);
        newcell2.setAttribute("id", "1cell" + i);
        newcell2.setAttribute("contenteditable", "true");
        newcell3.setAttribute("contenteditable", "true");
        newcell4.setAttribute("contenteditable", "true");
        newcell5.setAttribute("contenteditable", "true");
        newcell3.setAttribute("id", "2cell" + i);
        newcell4.setAttribute("id", "3cell" + i);
        newcell5.setAttribute("id", "4cell" + i);
      }

      for (i = 0; i < 4; i++) {
        document.getElementById("name" + i).innerHTML =
          accessedPersons[i].name.first + " " + accessedPersons[i].name.last;
      }

      var d1 = new Date();

      for (i = 0; i < 30; i++) {
        document.getElementById("date" + i).innerHTML = i + 1 + "/" + 11;
      }
      var data1 = [];
      let percentagecell1 = row2.insertCell(-1);

      var data2 = [];
      let percentagecell2 = row3.insertCell(-1);
      var data3 = [];
      let percentagecell3 = row4.insertCell(-1);
      var data4 = [];
      let percentagecell4 = row5.insertCell(-1);

      var negative = 0;
      var positive = 0;
      var neutral = 0;

      for (i = 0; i < 4; i++) {
        document.getElementById("1cell" + i).innerHTML =
          accessedPersons[i].attendance[i];
        data1.push(accessedPersons[i].attendance[i]);
         
      }

      for (i = 0; i < 30; i++) {
        document.getElementById("1cell" + i).oninput = function() {
          var test = document.getElementById("1cell" + i).innerHTML;
          console.log(test);
          data1.push(test);
          console.log(data1[i]);
      
        };


      }
        percentage();   

      document.getElementById("save").onclick = function() {
      
      };

      function percentage() {
        for (i = 0; i < 30; i++) {
          if (data1[i] == "a") {
            negative = negative + 1;
          }
          if (
            data1[i] == "s" ||
            data1[i] == "l" ||
            data1[i] == "nr" ||
            data1[i] == "e"
          ) {
            neutral = neutral + 1;
          }
          if (data1[i] == "p") {
            positive = positive + 1;
          }
          var totalvalue = positive + negative;
          var percentage = (positive / totalvalue) * 100;
          var n = percentage.toFixed(2);
          percentagecell1.innerHTML = n;
        }
      }
     
      negative = 0;
      positive = 0;
      neutral = 0;

      for (i = 0; i < 4; i++) {
        let data2 = (document.getElementById("2cell" + i).innerHTML =
          accessedPersons[1].attendance[i]);
        if (data2[i] == "a") {
          negative = negative + 1;
        }
        if (
          data2[i] == "s" ||
          data2[i] == "l" ||
          data2[i] == "nr" ||
          data2[i] == "e"
        ) {
          neutral = neutral + 1;
        }
        if (data2[i] == "p") {
          positive = positive + 1;
        }
        var totalvalue = positive + negative;
        var percentage = (positive / totalvalue) * 100;
        var n = percentage.toFixed(2);
        percentagecell2.innerHTML = n;
      }

      negative = 0;
      positive = 0;
      neutral = 0;

      for (i = 0; i < 4; i++) {
        let data3 = (document.getElementById("3cell" + i).innerHTML =
          accessedPersons[2].attendance[i]);
        if (data3[i] == "a") {
          negative = negative + 1;
        }
        if (
          data3[i] == "s" ||
          data3[i] == "l" ||
          data3[i] == "nr" ||
          data3[i] == "e"
        ) {
          neutral = neutral + 1;
        }
        if (data3[i] == "p") {
          positive = positive + 1;
        }
        var totalvalue = positive + negative;
        var percentage = (positive / totalvalue) * 100;
        var n = percentage.toFixed(2);
        percentagecell3.innerHTML = n;
      }

      negative = 0;
      positive = 0;
      neutral = 0;
      for (i = 0; i < 4; i++) {
        let data4 = (document.getElementById("4cell" + i).innerHTML =
          accessedPersons[3].attendance[i]);
        if (data4[i] == "a") {
          negative = negative + 1;
        }
        if (
          data4[i] == "s" ||
          data4[i] == "l" ||
          data4[i] == "nr" ||
          data4[i] == "e"
        ) {
          neutral = neutral + 1;
        }
        if (data4[i] == "p") {
          positive = positive + 1;
        }
        var totalvalue = positive + negative;
        var percentage = (positive / totalvalue) * 100;
        var n = percentage.toFixed(2);
        percentagecell4.innerHTML = n;
      }
    }
  }
};
</script>

<style>
#attendance {
  font-family: Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  max-width: 100%;

  margin: 25px;
  margin-top: 50px;
}

#attendance td,
#attendance th {
  border: 1px solid #ddd;
  padding: 8px;
  max-height: 20px;
}

#month {
  max-width: 200px;
}

#attendance th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  background-color: #4caf50;
  color: white;
}
</style>
