<html>
<head>
<link rel="stylesheet" href="stylesheet.css">
</head>
  <body>
    <h1> <u> Filter results by </u> </h1>
    
    <p> Link name: <input id='myInput' onkeyup='searchTable()' type='text' placeholder='Type here'> </p> 
    <p> Crossing number: <input id='myInput2' onkeyup='searchTable()' type='text' placeholder='Type here'> </p>
    <p> Volume: Greater than <input id='myInput4' onkeyup='searchTable()' type='text' placeholder='Type here'>, less than <input id='myInput3' onkeyup='searchTable()' type='text' placeholder='Type here'> </p>
    <p> No. tetrahedra: <input id='myInput5' onkeyup='searchTable()' type='text' placeholder='Type here'> </p>
    
    <h1> <u> Table </u> </h1>
    
      <table class="dataframe" id='myTable'>
      <thead>
        <tr style="text-align: right;" class='header'>
          <th></th>
          <th>Link Name</th>
          <th>No. Crossings</th>
          <th>Volume</th>
          <th>No. Tetrahedra</th>
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
        <tr>
      <th>2</th>
      <td>L8a15</td>
      <td>8</td>
      <td>8.967361</td>
      <td>10</td>
    </tr>
    <tr>
      <th>3</th>
      <td>L8a16</td>
      <td>8</td>
      <td>9.802001</td>
      <td>10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>L8a17</td>
      <td>8</td>
      <td>8.793346</td>
      <td>9</td>
    </tr>
    <tr>
      <th>5</th>
      <td>L8a18</td>
      <td>8</td>
      <td>6.551743</td>
      <td>7</td>
    </tr>
    <tr>
      <th>6</th>
      <td>L8a19</td>
      <td>8</td>
      <td>10.666979</td>
      <td>12</td>
    </tr>
    <tr>
      <th>7</th>
      <td>L8n4</td>
      <td>8</td>
      <td>5.333490</td>
      <td>6</td>
    </tr>
    <tr>
      <th>8</th>
      <td>L9a43</td>
      <td>9</td>
      <td>12.276563</td>
      <td>13</td>
    </tr>
    <tr>
      <th>9</th>
      <td>L9a44</td>
      <td>9</td>
      <td>11.294969</td>
      <td>12</td>
    </tr>
    <tr>
      <th>10</th>
      <td>L9a45</td>
      <td>9</td>
      <td>9.665346</td>
      <td>11</td>
    </tr>
    <tr>
      <th>11</th>
      <td>L9a46</td>
      <td>9</td>
      <td>13.323361</td>
      <td>14</td>
    </tr>
    <tr>
      <th>12</th>
      <td>L9a47</td>
      <td>9</td>
      <td>11.762234</td>
      <td>12</td>
    </tr>
    <tr>
      <th>13</th>
      <td>L9a48</td>
      <td>9</td>
      <td>9.312341</td>
      <td>10</td>
    </tr>
    <tr>
      <th>14</th>
      <td>L9a49</td>
      <td>9</td>
      <td>10.562806</td>
      <td>11</td>
    </tr>
    <tr>
      <th>15</th>
      <td>L9a50</td>
      <td>9</td>
      <td>10.740258</td>
      <td>12</td>
    </tr>
    <tr>
      <th>16</th>
      <td>L9a51</td>
      <td>9</td>
      <td>13.040401</td>
      <td>14</td>
    </tr>
    <tr>
      <th>17</th>
      <td>L9n20</td>
      <td>9</td>
      <td>9.966512</td>
      <td>11</td>
    </tr>
    <tr>
      <th>18</th>
      <td>L9n21</td>
      <td>9</td>
      <td>5.333490</td>
      <td>6</td>
    </tr>
    <tr>
      <th>19</th>
      <td>L9n22</td>
      <td>9</td>
      <td>8.355502</td>
      <td>9</td>
    </tr>
    <tr>
      <th>20</th>
      <td>L9n23</td>
      <td>9</td>
      <td>5.333490</td>
      <td>6</td>
    </tr>
    <tr>
      <th>21</th>
      <td>L9n24</td>
      <td>9</td>
      <td>7.706912</td>
      <td>8</td>
    </tr>
    <tr>
      <th>22</th>
      <td>L10a122</td>
      <td>10</td>
      <td>14.390332</td>
      <td>15</td>
    </tr>
    <tr>
      <th>23</th>
      <td>L10a123</td>
      <td>10</td>
      <td>13.955867</td>
      <td>15</td>
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
      input5 = document.getElementById("myInput5");
      filter = input.value.toUpperCase();
      filter2 = input2.value;
      filter3 = input3.value;
      filter4 = input4.value;
      filter5 = input5.value;
      table = document.getElementById("myTable");
      tr = table.getElementsByTagName("tr");
      for (i = 1; i < tr.length; i++) {
          td = tr[i].getElementsByTagName("td");
          if (!filter || td[0].innerHTML.toUpperCase().indexOf(filter) > -1) {
                  if (!filter2 || td[1].innerHTML === filter2) {
                    if (!filter3 || parseFloat(td[2].innerHTML) <= parseFloat(filter3)) {
                      if (!filter4 || parseFloat(td[2].innerHTML) >= parseFloat(filter4)) {
                        if (!filter5 || td[3].innerHTML === filter5) {
                          found = true;
                        }
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
