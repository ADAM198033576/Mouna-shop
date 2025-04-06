<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>البحث عن المنتج</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      direction: rtl;
      text-align: center;
      padding: 50px;
      background-color: #2e7d32; /* خلفية خضراء */
      color: white;
    }

    #logo {
      width: 200px; /* تعديل حجم اللوجو */
      margin-bottom: 20px;
    }

    input, button {
      padding: 10px;
      font-size: 16px;
      margin: 10px;
      border: none;
      border-radius: 5px;
    }

    input {
      width: 200px;
    }

    button {
      background-color: white;
      color: #2e7d32;
      font-weight: bold;
      cursor: pointer;
    }

    button:hover {
      background-color: #c8e6c9;
    }

    #result {
      margin-top: 20px;
      font-size: 18px;
      color: #fffde7; /* أصفر فاتح */
    }

    .product-card {
      background: white;
      color: black;
      padding: 20px;
      margin-top: 20px;
      border-radius: 10px;
      display: inline-block;
      text-align: center;
    }

    .product-card img {
      width: 150px;
      height: 150px;
      border-radius: 10px;
      margin-bottom: 10px;
    }
  </style>
</head>
<body>

  <img id="logo" src="WhatsApp Image 2024-11-25 at 22.09.41.jpeg" alt="شعار Mouna Shop">

  <h2>أدخل كود المنتج</h2>
  <input type="text" id="productCode" placeholder="مثال: XYZ123">
  <button onclick="searchProduct()">إظهار المنتج</button>

  <div id="result"></div>

  <script>
    const products = {
      "10-0103": { name:"GEL VISAGE NETTOYANT – TOUS TYPES DE PEAUX FLEUR D’ORANGER", price: "0 درهم", image: "WhatsApp Image 2024-12-21 at 22.22.26.jpeg" },
      "10-0104": { name:"GEL VISAGE NETTOYANT – PEAUX SECHES A L’ACIDE HYALURONIQUE", price: "0 درهم", image: "ءءءءءء.jpg" },
      "DEF456": { name: "مقشر السكر بالفانيلا", price: "55 درهم", image: "vanilla_scrub.jpg" }
    };

    function searchProduct() {
      const code = document.getElementById("productCode").value.trim().toUpperCase();
      const product = products[code];

      const resultDiv = document.getElementById("result");
      if (product) {
        resultDiv.innerHTML = `
          <div class="product-card">
            <img src="${product.image}" alt="${product.name}">
            <p><strong>📦 ${product.name}</strong></p>
            <p>💵 الثمن: <strong>${product.price}</strong></p>
          </div>
        `;
      } else {
        resultDiv.innerHTML = "🚫 كود المنتج غير صحيح!";
      }
    }
  </script>

</body>
</html>
