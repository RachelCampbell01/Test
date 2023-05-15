<html>
<head>
<link rel="stylesheet" href="stylesheet.css">
</head>
  <body>
    <p> Filter by link name: <input id='myInput' onkeyup='searchTable()' type='text' placeholder='Type here to search'> </p> 
    <p> Filter by crossing number: <input id='myInput2' onkeyup='searchTable()' type='text' placeholder='Type here to search part 2'> </p>
    <p> Filter by volume: </p>
    <p> Less than: <input id='myInput3' onkeyup='searchTable()' type='text' placeholder='Type here to search part 3'>. Greater than: <input id='myInput4' onkeyup='searchTable()' type='text' placeholder='Type here to search part 4'>. </p>
    <br>
    
      <table class="dataframe" id='myTable'>
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
          <td>60</td>
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
      input2 = document.getElementById("myInput2");
      input3 = document.getElementById("myInput3");
      input4 = document.getElementById("myInput4");
      filter = input.value.toUpperCase();
      filter2 = input2.value;
      filter3 = input3.value;
      filter4 = input4.value;
      table = document.getElementById("myTable");
      tr = table.getElementsByTagName("tr");
      for (i = 1; i < tr.length; i++) {
          td = tr[i].getElementsByTagName("td");
          if (filter == "" || td[0].innerHTML.toUpperCase().indexOf(filter) > -1) {
                  if (filter2 == "" || td[1].innerHTML === filter2) {
                    if (filter3 == "" || parseFloat(td[2].innerHTML) <= parseFloat(filter3)) {
                      if (filter4 == "" || parseFloat(td[2].innerHTML) >= parseFloat(filter4) {
                        found = true;
                      }
                    }
                  }
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
