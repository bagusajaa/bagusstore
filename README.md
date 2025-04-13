# bagusstore
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Top Up Game</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="container">
    <h1>Top Up Game Murah</h1>

    <form id="topup-form">
      <label for="game">Pilih Game:</label>
      <select id="game" required>
        <option value="">-- Pilih Game --</option>
        <option value="mobile-legends">Mobile Legends</option>
        <option value="free-fire">Free Fire</option>
        <option value="pubg">PUBG Mobile</option>
      </select>

      <label for="userid">ID Pemain:</label>
      <input type="text" id="userid" placeholder="Masukkan ID kamu" required>

      <label for="nominal">Nominal Top Up:</label>
      <select id="nominal" required>
        <option value="">-- Pilih Nominal --</option>
        <option value="10">10 Diamonds - Rp 1.500</option>
        <option value="50">50 Diamonds - Rp 7.000</option>
        <option value="100">100 Diamonds - Rp 13.000</option>
      </select>

      <button type="submit">Kirim Pesanan</button>
    </form>

    <div id="pesan-sukses" class="hidden">
      <p>Pesanan kamu sudah dikirim! Silakan tunggu konfirmasi.</p>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  background-color: #f1f1f1;
  display: flex;
  justify-content: center;
  padding-top: 50px;
}

.container {
  background-color: white;
  padding: 30px;
  border-radius: 12px;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
  width: 90%;
  max-width: 400px;
}

h1 {
  text-align: center;
  margin-bottom: 20px;
}

label {
  display: block;
  margin-top: 10px;
}

input, select, button {
  width: 100%;
  padding: 10px;
  margin-top: 5px;
  border-radius: 6px;
  border: 1px solid #ccc;
  margin-bottom: 10px;
}

button {
  background-color: #007bff;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

.hidden {
  display: none;
}
document.getElementById("topup-form").addEventListener("submit", function(e) {
  e.preventDefault();

  // Ambil data form
  const game = document.getElementById("game").value;
  const userId = document.getElementById("userid").value;
  const nominal = document.getElementById("nominal").value;

  if (game && userId && nominal) {
    console.log("Pesanan dikirim:", { game, userId, nominal });

    document.getElementById("pesan-sukses").classList.remove("hidden");
    this.reset();
  }
});
