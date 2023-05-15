<html>
  <body>
    <h> Hello </h> <br>
    <input id='myInput' onkeyup='searchTable()' type='text' placeholder='Type here to search'> <br>
    <input id='myInput2' onkeyup='searchTable2()' type='text' placeholder='Type here to search part 2'> <br>
    
      <table border="1" class="dataframe" id='myTable'>
      <thead>
        <tr style="text-align: right;" class='header'>
          <th></th>
          <th>LinkName</th>
          <th>No.Crossings</th>
          <th>Volume</th>
          <th>No.Tetrahedra</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>0</th>
          <td>L6a5</td>
          <td>6</td>
          <td>5.333490</td>
          <td>6</td>
        </tr>
        <tr>
          <th>1</th>
          <td>L7a7</td>
          <td>7</td>
          <td>7.706912</td>
          <td>8</td>
        </tr>
      </tbody>
    </table>
    <script>
    function searchTable() {
      var input, filter, found, table, tr, td, i, j;
      input = document.getElementById("myInput");
      filter = input.value.toUpperCase();
      table = document.getElementById("myTable");
      tr = table.getElementsByTagName("tr");
      for (i = 1; i < tr.length; i++) {
          td = tr[i].getElementsByTagName("td");
          if (td[0].innerHTML.toUpperCase().indexOf(filter) > -1) {
                  found = true;
          }
          if (found) {
              tr[i].style.display = "";
              found = false;
          } else {
              tr[i].style.display = "none";
          }
      }
    }
      
    function searchTable() {
      var input, filter, found, table, tr, td, i, j;
      input = document.getElementById("myInput");
      filter = input.value.toUpperCase();
      table = document.getElementById("myTable");
      tr = table.getElementsByTagName("tr");
      for (i = 1; i < tr.length; i++) {
          td = tr[i].getElementsByTagName("td");
          if (td[1].innerHTML.toUpperCase().indexOf(filter) > -1) {
                  found = true;
          }
          if (found) {
              tr[i].style.display = "";
              found = false;
          } else {
              tr[i].style.display = "none";
          }
      }
    }
    </script>
  </body>
</html>
