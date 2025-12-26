# DLX
<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Delivery Laundry X</title>
<style>
body {
  font-family: sans-serif;
  background: #000;
  color: #fff;
  padding: 20px;
}
h1 {
  color: red;
  text-align: center;
}
.card {
  background: #111;
  padding: 15px;
  border-radius: 10px;
  margin-bottom: 15px;
}
button {
  background: red;
  color: #fff;
  border: none;
  padding: 15px;
  width: 100%;
  border-radius: 10px;
  font-size: 16px;
}
input, select {
  width: 100%;
  padding: 10px;
  border-radius: 8px;
  border: none;
}
.total {
  font-size: 20px;
  color: red;
}
</style>
</head>

<body>

<h1>Delivery Laundry X</h1>

<div class="card">
<label>ช่วงเวลา</label>
<select id="time">
  <option value="day">ก่อน 21:30</option>
  <option value="night">หลัง 21:30</option>
</select>
</div>

<div class="card">
<label>นน.ขนส่ง (kg)</label>
<input type="number" id="weight" value="10">
</div>

<div class="card">
<label>ระยะทาง</label>
<select id="distance">
  <option value="0.5">ไม่เกิน 500 เมตร</option>
  <option value="1">500m - 1km</option>
</select>
</div>

<div class="card total">
รวมทั้งหมด: <span id="price">0</span> บาท
</div>

<button onclick="calc()">ยืนยันการจอง</button>

<script>
function calc() {
  let time = document.getElementById("time").value;
  let weight = document.getElementById("weight").value;
  let distance = document.getElementById("distance").value;

  let delivery = 0;
  if (time === "day") {
    delivery = distance == 0.5 ? 20 : 30;
  } else {
    delivery = distance == 0.5 ? 30 : 40;
  }

  let weightFee = weight * 2;
  document.getElementById("price").innerText = delivery + weightFee;
}
</script>

</body>
</html>

