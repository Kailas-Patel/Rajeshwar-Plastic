<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>order form - Rajeshwar Plastic</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Poppins', sans-serif;
      padding: 30px;
      margin: 0;
      background: linear-gradient(to right, #d4fc79, #96e6a1);
    }

    h1, h2 {
      color: #333;
      text-align: center;
    }

    h1 {
      font-size: 36px;
      font-weight: 600;
      margin-bottom: 10px;
    }

    h2 {
      font-size: 24px;
      margin-top: 30px;
      margin-bottom: 15px;
    }

    .form-section {
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
      margin-bottom: 30px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin-bottom: 15px;
    }

    th, td {
      border: 1px solid #ccc;
      padding: 10px;
      text-align: left;
    }

    select, input[type="number"], input[type="text"], input[type="tel"] {
      width: 100%;
      padding: 8px;
      border: 1px solid #aaa;
      border-radius: 5px;
      margin-bottom: 10px;
    }

    button {
      padding: 10px 20px;
      background-color: #28a745;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: background-color 0.3s ease;
      font-weight: 600;
      margin-top: 10px;
    }

    button:hover {
      background-color: #218838;
    }

    .submit-button {
      text-align: center;
    }

    input[type="submit"] {
      padding: 12px 24px;
      font-size: 16px;
      font-weight: bold;
      color: white;
      background-color: #007bff;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: background 0.3s ease;
    }

    input[type="submit"]:hover {
      background-color: #0056b3;
    }
  </style>
</head>
<body>

  <h1>RAJESHWAR PLASTIC</h1>
  <h2>Bag Order Form</h2>

  <form id="orderForm" onsubmit="sendToWhatsApp(event)">

    <!-- Customer Info -->
    <div class="form-section">
      <label><strong>Customer Name</strong></label>
      <input type="text" id="name" required>

      <label><strong>Phone Number</strong></label>
      <input type="tel" id="phone" required>
    </div>

    <!-- LD Bags -->
    <div class="form-section">
      <h2>LD Bags</h2>
      <table id="ldTable">
        <thead><tr><th>Size</th><th>Quantity</th></tr></thead>
        <tbody>
          <tr>
            <td>
              <select name="ldSize[]">
                <option value="">Select Size</option>
                <option value="5x6">5x6</option>
                <option value="5x7">5x7</option>
                <option value="5.5x8">5.5x8</option>
                <option value="5x24">5x24(300g)</option>
                <option value="6x6">6x6</option>
                <option value="6x7">6x7</option>
                <option value="6x8">6x8</option>
                <option value="6x24">6x24(300g)</option>
                <option value="7x8">7x8</option>
                <option value="7x9">7x9</option>
                <option value="7x24">7x24(300g)</option>
                <option value="8x10">8x10</option>
                <option value="8x24">8x24(300g)</option>
                <option value="9x11">9x11</option>
                <option value="10x12">10x12</option>
                <option value="10x14">10x14</option>
                <option value="12x14">12x14</option>
                <option value="12x16">12x16</option>
                <option value="12x18">12x18</option>
                <option value="12x20">12x20</option>
                <option value="14x16">14x16</option>
                <option value="14x21">14x21</option>
                <option value="16x18">16x18</option>
                <option value="18x20">18x20</option>
             </select>
            </td>
            <td><input type="number" name="ldQty[]" min="1"></td>
          </tr>
        </tbody>
      </table>
      <button type="button" onclick="addRow('ldTable')">Add LD Bag</button>
    </div>

    <!-- PP Bags -->
    <div class="form-section">
      <h2>PP Bags</h2>
      <table id="ppTable">
        <thead><tr><th>Size</th><th>Quantity</th></tr></thead>
        <tbody>
          <tr>
            <td>
              <select name="ppSize[]">
                <option value="">Select Size</option>
                <option value="5x6">5x6</option>
                <option value="5x7">5x7</option>
                <option value="6x6">6x6</option>
                <option value="6x7">6x7</option>
                <option value="6x8">6x8</option>
                <option value="6x24">6x24(300g)</option>
                <option value="7x8">7x8</option>
                <option value="7x9">7x9</option>
                <option value="7x24">7x24(300g)</option>
                <option value="8x10">8x10</option>
                <option value="8x24">8x24(300g)</option>
                <option value="9x11">9x11</option>
                <option value="10x12">10x12</option>
                <option value="12x14">12x14</option>
                <option value="14x16">14x16</option>
                <option value="16x18">16x18</option>
                <option value="18x20">18x20</option>
              </select>
            </td>
            <td><input type="number" name="ppQty[]" min="1"></td>
          </tr>
        </tbody>
      </table>
      <button type="button" onclick="addRow('ppTable')">Add PP Bag</button>
    </div>

<!-- Custom Size Bags -->
<div class="form-section">
  <h2>Custom Size Bags</h2>
  <table id="customTable">
    <thead>
      <tr>
       <th>Size</th>
       <th>Quality</th>
       <th>Quantity</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><input type="text" name="customSize[]" placeholder="e.g., 6.5x9"></td>
        <td><input type="text" name="customQuality[]" placeholder="e.g., LD or PP(and gage)"></td>
        <td><input type="number" name="customQty[]" min="1" placeholder="Enter quantity"></td>
      </tr>
    </tbody>
  </table>
  <button type="button" onclick="addRow('customTable')">Add Custom Size</button>
</div>

<!-- Stretch Film (on order only)-->
<div class="form-section">
  <h2>Stretch Film (on order onlt)</h2>
  <table id="customTable">
    <thead>
      <tr>
       <th>Size</th>
       <th>Quantity</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><input type="text" name="customSize[]" placeholder="e.g., 6.5x9"></td>
        <td><input type="number" name="customQty[]" min="1 box" placeholder=" Minimum 1 Box"></td>
      </tr>
    </tbody>
  </table>
  <button type="button" onclick="addRow('customTable')">Add Custom Size</button>
</div>

<!-- Shrink Bag/Roll (on order only)-->
<div class="form-section">
  <h2>Shrink Bag/Roll(on order)</h2>
  <table id="customTable">
    <thead>
      <tr>
       <th>Size</th>
       <th>Quantity</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><input type="text" name="customSize[]" placeholder="e.g., 6.5x9"></td>
        <td><input type="number" name="customQty[]" min="1 box" placeholder=" Min 1 Full Bag (approx 40kg)"></td>
      </tr>
    </tbody>
  </table>
  <button type="button" onclick="addRow('customTable')">Add Custom Size</button>
</div>

<!-- Courier Bag (on order only)-->
<div class="form-section">
  <h2>Courier Bag (on order)</h2>
  <table id="customTable">
    <thead>
      <tr>
       <th>Size</th>
       <th>Quantity</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><input type="text" name="customSize[]" placeholder="e.g., 6.5x9"></td>
        <td><input type="number" name="customQty[]" min="1 box" placeholder=" Min 1 Full Bag (approx 40kg)"></td>
      </tr>
    </tbody>
  </table>
  <button type="button" onclick="addRow('customTable')">Add Custom Size</button>
</div>

    <!-- More Material -->
    <div class="form-section">
      <h2>More Material</h2>
      <table id="materialTable">
        <thead><tr><th>Material</th><th>Quantity</th></tr></thead>
        <tbody>
          <tr>
            <td>
              <select name="material[]">
                <option value="">Select Material</option>
                <option>Packing Patti Roll (2kg)</option>
                <option>Packing Patti Roll (10kg)</option>
                <option>Clip</option>
                <option>Corrugated Roll</option>
                <option>Selo-Tape</option>
                <option>No. 10 Stapler Pin</option>
                <option>24/6 Stapler Pin</option>
                <option>Eagle Machine Set (Tensioner and Sealer)</option>
                <option>Falcon Machine Set (Tensioner and Sealer)</option>
                <option>Marker Pen (Red)</option>
                <option>Marker Pen (Blue)</option>
                <option>Marker Pen (Black)</option>
              </select>
            </td>
            <td><input type="number" name="materialQty[]" min="1"></td>
          </tr>
        </tbody>
      </table>
      <button type="button" onclick="addRow('materialTable')">Add Material</button>
    </div>

    <!-- Plastic Sutli -->
    <div class="form-section">
      <h2>Plastic Sutli</h2>
      <table id="sutliTable">
        <thead><tr><th>Brand & Rate</th><th>Kg</th></tr></thead>
        <tbody>
          <tr>
            <td>
              <select name="sutli[]">
                <option value="">Select Brand</option>
                <option>Neha (₹140/kg)</option>
                <option>Packer (₹185/kg)</option>
                <option>Dolphine (₹150/kg)</option>
                <option>Kangaroo (₹85/kg)</option>
                <option>Neha Gold (₹120/kg)</option>
                <option>Wonder Pack (₹180/kg)</option>
              </select>
            </td>
            <td><input type="number" name="sutliQty[]" min="1"></td>
          </tr>
        </tbody>
      </table>
      <button type="button" onclick="addRow('sutliTable')">Add Sutli</button>
    </div>
    <!-- Separate Colors -->
<div class="form-section">
  <h2>Separate Colors</h2>
  <table id="colorTable">
    <thead>
      <tr>
        <th>Color Name</th>
        <th>Weight</th>
        <th>Quantity</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>
          <select name="colorName[]">
            <option value="">Select Color</option>
            <option>Blue</option>
            <option>Green</option>
            <option>Magenta</option>
            <!-- Add more if needed -->
          </select>
        </td>
        <td>
          <select name="colorWeight[]">
            <option value="">Select Weight</option>
            <option>100g</option>
            <option>500g</option>
            <option>1kg</option>
          </select>
        </td>
        <td><input type="number" name="colorQty[]" min="1"></td>
      </tr>
    </tbody>
  </table>
  <button type="button" onclick="addRow('colorTable')">Add Color</button>
</div>
    <!-- Submit -->
    <div class="submit-button">
      <input type="submit" value="Submit Order via WhatsApp">
    </div>

  </form>

  <script>
    function addRow(tableId) {
      const table = document.getElementById(tableId).getElementsByTagName('tbody')[0];
      const newRow = table.rows[0].cloneNode(true);
      const inputs = newRow.querySelectorAll('input, select');
      inputs.forEach(input => {
        input.tagName === 'SELECT' ? input.selectedIndex = 0 : input.value = '';
      });
      table.appendChild(newRow);
    }

    function sendToWhatsApp(event) {
      event.preventDefault();

      const name = document.getElementById("name").value;
      const phone = document.getElementById("phone").value;
      let message = `*RAJESHWAR PLASTIC ORDER*\n👤 Name: ${name}\n📞 Phone: ${phone}\n\n`;

      const collectItems = (label, names, qtys) => {
        let output = `🔹 *${label}*\n`;
        for (let i = 0; i < names.length; i++) {
          const item = names[i].value;
          const qty = qtys[i].value;
          if (item && qty) output += `• ${item} - ${qty}\n`;
        }
        return output + '\n';
      };

      message += collectItems('LD Bags',
        document.getElementsByName('ldSize[]'),
        document.getElementsByName('ldQty[]'));
      message += collectItems('PP Bags',
        document.getElementsByName('ppSize[]'),
        document.getElementsByName('ppQty[]'));
      message += collectItems('More Materials',
        document.getElementsByName('material[]'),
        document.getElementsByName('materialQty[]'));
      message += collectItems('Plastic Sutli',
        document.getElementsByName('sutli[]'),
        document.getElementsByName('sutliQty[]'));
      message += collectItems('Marka Color',
        document.getElementsByName('marka[]'),
        document.getElementsByName('markaQty[]'));

      const encodedMsg = encodeURIComponent(message);
      const whatsappNumber = "919594459534"; // Replace with your number
      const url = `https://wa.me/${whatsappNumber}?text=${encodedMsg}`;
      window.open(url, '_blank');
    }
  </script>

</body>
</html>
