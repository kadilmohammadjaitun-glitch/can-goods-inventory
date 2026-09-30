<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Can Goods Inventory</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: #f1f5f1;
            color: #222;
        }

        .header {
            background: #176b3a;
            color: white;
            padding: 20px;
            text-align: center;
        }

        .header h1 {
            margin: 0;
            font-size: 24px;
        }

        .header p {
            margin: 5px 0 0;
            font-size: 14px;
        }

        .container {
            padding: 15px;
            max-width: 600px;
            margin: auto;
        }

        .cards {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
        }

        .card {
            background: white;
            padding: 18px;
            border-radius: 12px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
        }

        .card h2 {
            margin: 0;
            color: #176b3a;
            font-size: 28px;
        }

        .card p {
            margin: 5px 0 0;
            color: #666;
        }

        .scanner {
            background: white;
            margin-top: 15px;
            padding: 18px;
            border-radius: 12px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
        }

        .scanner h3 {
            margin-top: 0;
        }

        input {
            width: 100%;
            padding: 14px;
            border: 1px solid #ccc;
            border-radius: 8px;
            font-size: 16px;
        }

        button {
            width: 100%;
            padding: 14px;
            margin-top: 10px;
            border: none;
            border-radius: 8px;
            background: #176b3a;
            color: white;
            font-size: 16px;
            font-weight: bold;
        }

        button:active {
            transform: scale(0.98);
        }

        .scan-button {
            background: #e6a900;
        }

        #result {
            margin-top: 15px;
            padding: 12px;
            border-radius: 8px;
            background: #eef7ef;
            display: none;
        }
    </style>
</head>

<body>

    <div class="header">
        <h1>🥫 Can Goods Inventory</h1>
        <p>Inventory Management System</p>
    </div>

    <div class="container">

        <div class="cards">

            <div class="card">
                <h2 id="products">0</h2>
                <p>Products</p>
            </div>

            <div class="card">
                <h2 id="stock">0</h2>
                <p>Total Stock</p>
            </div>

            <div class="card">
                <h2 id="lowstock">0</h2>
                <p>Low Stock</p>
            </div>

            <div class="card">
                <h2 id="outstock">0</h2>
                <p>Out of Stock</p>
            </div>

        </div>

        <div class="scanner">

            <h3>📷 Barcode Scanner</h3>

            <button class="scan-button" onclick="scanBarcode()">
                📷 SCAN BARCODE
            </button>

            <p>Or enter barcode manually:</p>

            <input
                type="text"
                id="barcode"
                placeholder="Enter barcode number"
            >

            <button onclick="searchBarcode()">
                🔍 SEARCH BARCODE
            </button>

            <div id="result"></div>

        </div>

    </div>

    <script>

        function searchBarcode() {

            let barcode =
                document.getElementById("barcode").value;

            let result =
                document.getElementById("result");

            if (barcode === "") {

                result.style.display = "block";
                result.innerHTML =
                    "⚠️ Please enter a barcode.";

                return;
            }

            result.style.display = "block";

            result.innerHTML =
                "<strong>Barcode:</strong> " +
                barcode +
                "<br><br>" +
                "🔎 Searching product...";

        }

        function scanBarcode() {

            alert(
                "Barcode camera scanner will be added in the next step."
            );

        }

    </script>

</body>
</html>
