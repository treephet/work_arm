<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>สูตรคูณ</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 500px;
            text-align: center;
        }
        h1 {
            color: #333;
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 10px;
            font-size: 1.2em;
            color: #555;
        }
        input {
            width: 100%;
            padding: 10px;
            font-size: 1em;
            border: 1px solid #ddd;
            border-radius: 4px;
            margin-bottom: 20px;
            box-sizing: border-box;
        }
        button {
            background-color: #007BFF;
            color: #fff;
            border: none;
            padding: 10px 20px;
            font-size: 1em;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        button:hover {
            background-color: #0056b3;
        }
        #result {
            margin-top: 20px;
            text-align: left;
        }
        .table {
            border-collapse: collapse;
            width: 100%;
            margin: 0 auto;
        }
        .table th, .table td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: center;
        }
        .table th {
            background-color: #007BFF;
            color: #fff;
        }
        .table tr:nth-child(even) {
            background-color: #f9f9f9;
        }
        .table tr:hover {
            background-color: #f1f1f1;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>สูตรคูณ</h1>
        <label for="numberInput">กรุณาใส่ตัวเลข:</label>
        <input type="number" id="numberInput" min="1" max="100">
        <button onclick="generateTable()">แสดงตารางสูตรคูณ</button>
        
        <div id="result"></div>
    </div>
    
    <script>
        function generateTable() {
            const number = parseInt(document.getElementById('numberInput').value);
            const resultDiv = document.getElementById('result');
            resultDiv.innerHTML = ''; // Clear previous results
            
            if (isNaN(number)) {
                resultDiv.innerHTML = '<p style="color: red;">กรุณาใส่ตัวเลขที่ถูกต้อง</p>';
                return;
            }

            let tableHtml = '<table class="table">';
            tableHtml += '<tr><th>คูณ</th><th>ผลลัพธ์</th></tr>';
            for (let i = 1; i <= 12; i++) {
                tableHtml += `<tr><td>${number} × ${i}</td><td>${number * i}</td></tr>`;
            }
            tableHtml += '</table>';
            resultDiv.innerHTML = tableHtml;
        }
    </script>
</body>
</html>
