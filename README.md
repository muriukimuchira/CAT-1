# CAT-1<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Employee Pay Calculator</title>
<link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h2>Employee Pay Calculator</h2>
        <form id="payForm">
            <label for="employeeName">Employee Name:</label>
            <input type="text" id="employeeName" name="employeeName" required><br><br>

            <label for="hoursWorked">Hours Worked:</label>
            <input type="number" id="hoursWorked" name="hoursWorked" required><br><br>

            <label for="ratePerHour">Rate per Hour ($):</label>
            <input type="number" id="ratePerHour" name="ratePerHour" required><br><br>

            <button type="button" onclick="calculatePay()">Calculate Pay</button>
        </form>

        <div id="results" style="display: none;">
            <h3>Results</h3>
            <p><strong>Employee Name:</strong> <span id="resultName"></span></p>
            <p><strong>Basic Pay:</strong> $<span id="resultBasicPay"></span></p>
            <p><strong>Tax:</strong> $<span id="resultTax"></span></p>
            <p><strong>Net Pay:</strong> $<span id="resultNetPay"></span></p>
        </div>
    </div>
    <table>
        <table>
            <tr>
              <th>Descrption </th> 
              <th>amount</th>
             </tr>
             <tr>
              <td>Basicsalary</td>
              <td></td>
             </tr>
             <tr>
              <td>Grosssalary</td>
              <td></td>
             </tr>
             <tr>
              <td>InomeTax30%</td>
              <td></td>
             </tr>
             <tr>
              <td>Net pay</td>
              <td></td>
             </tr>
          </table>
          </body>
      </table>
      </body>

    
</body>
</html>
<style>
    body{
     margin:100px;
     font-family:Arial, Helvetica, sans-serif
    }
     h1 {
     color:red;
   }

    table{
      border-collapse:collapse;
      margin-top:24px;
      width:40%
    }

    th,
    td{
     border:2px solid greeNyellow;
     padding:10px;
     text-align:left;
    }
     th{
     background-color:rgb(147,144,144);

     }

 </style>
    

    <script src="script.js">
        function calculatePay() {
    // Fetching user inputs
    var employeeName = document.getElementById("employeeName").value;
    var hoursWorked = parseFloat(document.getElementById("hoursWorked").value);
    var ratePerHour = parseFloat(document.getElementById("ratePerHour").value);

    // Calculating basic pay
    var basicPay = hoursWorked * ratePerHour;

    // Calculating tax based on basic pay
    var tax;
    if (basicPay > 50000) {
        tax = 0.2 * basicPay;
    } else if (basicPay >= 20000) {
        tax = 0.1 * basicPay;
    } else {
        tax = 0; // No tax for basic pay below 20000
    }

    // Calculating net pay
    var netPay = basicPay - tax;

    // Displaying results in the HTML
    document.getElementById("resultName").textContent = employeeName;
    document.getElementById("resultBasicPay").textContent = basicPay.toFixed(2);
    document.getElementById("resultTax").textContent = tax.toFixed(2);
    document.getElementById("resultNetPay").textContent = netPay.toFixed(2);

    // Showing the results section
    document.getElementById("results").style.display = "block";
}

