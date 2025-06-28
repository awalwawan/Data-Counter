<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Form Pencatatan Counter</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f2f5;
      padding: 30px;
    }
    .form-container {
      max-width: 500px;
      margin: auto;
      background: white;
      padding: 25px 30px;
      box-shadow: 0 0 15px rgba(0,0,0,0.1);
      border-radius: 10px;
    }
    .form-container h2 {
      text-align: center;
      color: #333;
      margin-bottom: 20px;
    }
    label {
      display: block;
      margin-top: 15px;
      font-weight: bold;
    }
    input, select {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      margin-top: 20px;
      padding: 12px;
      width: 100%;
      background: #28a745;
      color: white;
      font-size: 16px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background: #218838;
    }
    .footer-text {
      margin-top: 30px;
      text-align: center;
      color: #666;
      font-style: italic;
    }
  </style>
</head>
<body>
  <div class="form-container">
    <h2>Pencatatan Counter</h2>
    <form id="counterForm">
      <label for="tanggal">Tanggal Bertugas</label>
      <input type="date" id="tanggal" name="tanggal" required>

      <label for="shift">Pilihan Shift</label>
      <select id="shift" name="shift" required>
        <option value="">-- Pilih Shift --</option>
        <option value="Shift 1">Shift 1</option>
        <option value="Shift 2">Shift 2</option>
        <option value="Shift 3">Shift 3</option>
      </select>

      <label for="gto01">Counter GTO 01</label>
      <input type="number" id="gto01" name="gto01"  required>

      <label for="gto02">Counter GTO 02</label>
      <input type="number" id="gto02" name="gto02" required>

      <label for="gardu03">Counter Gardu 03</label>
      <input type="number" id="gardu03" name="gardu03" required>

      <label for="gardu04">Counter Gardu 04</label>
      <input type="number" id="gardu04" name="gardu04" required>

      <label for="gto05">Counter GTO 05</label>
      <input type="number" id="gto05" name="gto05" required>

      <button type="submit">Kirim</button>
    </form>
    <div class="footer-text">
    <a href="[URL_TUJUAN](https://docs.google.com/spreadsheets/d/1-YZgNIkJshhQceFYaSvN-KGtVNId2_qWNT00BNPGdNE/edit?gid=293948849#gid=293948849&range=A1)">
  <button>Lihat Counter</button>
</a>
      Pencatatan Counter By AWAL
    </div>
  </div>

  <script>
    const form = document.getElementById('counterForm');
    form.addEventListener('submit', e => {
      e.preventDefault();
      const formData = new FormData(form);
      fetch('https://script.google.com/macros/s/AKfycbxPCm9f91Hp0pxectJL-6fZt7jp-KjbY4Y6cq7KOoEJdyPf0msiDEde-vvZvTIvkox_Lg/exec', {
        method: 'POST',
        body: formData
      })
      .then(response => {
        alert('Data berhasil dikirim!');
        form.reset();
      })
      .catch(error => {
        alert('Terjadi kesalahan. Silakan coba lagi.');
        console.error('Error!', error.message);
      });
    });
  </script>
</body>
</html>
