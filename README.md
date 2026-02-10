<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Smart City Dashboard</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #0f172a;
      color: #fff;
    }

    header {
      padding: 20px;
      background: linear-gradient(90deg, #2563eb, #22c55e);
      text-align: center;
      font-size: 24px;
      font-weight: bold;
    }

    .dashboard {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 20px;
      padding: 20px;
    }

    .card {
      background: #1e293b;
      border-radius: 12px;
      padding: 20px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.3);
    }

    .card h2 {
      margin: 0 0 10px;
      font-size: 18px;
      color: #38bdf8;
    }

    .value {
      font-size: 32px;
      font-weight: bold;
    }

    .status {
      margin-top: 10px;
      padding: 8px;
      border-radius: 8px;
      text-align: center;
      font-weight: bold;
    }

    .good { background: #16a34a; }
    .warning { background: #ca8a04; }
    .danger { background: #dc2626; }

    .alert {
      background: #dc2626;
      padding: 15px;
      border-radius: 12px;
      animation: blink 1.5s infinite;
    }

    @keyframes blink {
      0% { opacity: 1; }
      50% { opacity: 0.5; }
      100% { opacity: 1; }
    }

    footer {
      text-align: center;
      padding: 15px;
      opacity: 0.7;
    }
  </style>
</head>
<body>

<header>
  🌆 Smart City Live Dashboard
</header>

<div class="dashboard">

  <div class="card">
    <h2>City Health Score</h2>
    <div class="value" id="health">85%</div>
    <div class="status good">Healthy</div>
  </div>

  <div class="card">
    <h2>Traffic Congestion</h2>
    <div class="value" id="traffic">42%</div>
    <div class="status warning">Moderate</div>
  </div>

  <div class="card">
    <h2>Air Quality (AQI)</h2>
    <div class="value" id="air">68</div>
    <div class="status good">Good</div>
  </div>

  <div class="card">
    <h2>Energy Usage</h2>
    <div class="value" id="energy">73%</div>
    <div class="status warning">High Load</div>
  </div>

  <div class="card alert">
    🚨 ALERT<br>
    Heavy traffic expected in Downtown (20 min)
  </div>

</div>

<footer>
  Smart City • Real-Time Monitoring • AI Ready
</footer>

<script>
  function random(min, max) {
    return Math.floor(Math.random() * (max - min + 1)) + min;
  }

  function updateData() {
    document.getElementById("health").innerText = random(70, 95) + "%";
    document.getElementById("traffic").innerText = random(20, 90) + "%";
    document.getElementById("air").innerText = random(40, 120);
    document.getElementById("energy").innerText = random(50, 95) + "%";
  }

  setInterval(updateData, 3000);
</script>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Smart City Dashboard</title>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #0f172a;
      color: #fff;
    }

    header {
      padding: 20px;
      background: linear-gradient(90deg, #2563eb, #22c55e);
      text-align: center;
      font-size: 24px;
      font-weight: bold;
    }

    .dashboard {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 20px;
      padding: 20px;
    }

    .card {
      background: #1e293b;
      border-radius: 12px;
      padding: 20px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.3);
    }

    .card h2 {
      margin: 0 0 10px;
      font-size: 18px;
      color: #38bdf8;
    }

    .value {
      font-size: 32px;
      font-weight: bold;
    }

    .status {
      margin-top: 10px;
      padding: 8px;
      border-radius: 8px;
      text-align: center;
      font-weight: bold;
    }

    .good { background: #16a34a; }
    .warning { background: #ca8a04; }
    .danger { background: #dc2626; }

    .chart-container {
      background: #1e293b;
      border-radius: 12px;
      padding: 20px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.3);
      margin: 20px;
    }

    .alert {
      background: #dc2626;
      padding: 15px;
      border-radius: 12px;
      animation: blink 1.5s infinite;
    }

    @keyframes blink {
      0% { opacity: 1; }
      50% { opacity: 0.5; }
      100% { opacity: 1; }
    }

    footer {
      text-align: center;
      padding: 15px;
      opacity: 0.7;
    }
  </style>
</head>
<body>

<header>
  🌆 Smart City Live Dashboard
</header>

<div class="dashboard">

  <div class="card">
    <h2>Humidity</h2>
    <div class="value" id="humidity">55%</div>
    <div class="status good">Normal</div>
  </div>

  <div class="card">
    <h2>Temperature</h2>
    <div class="value" id="temperature">28°C</div>
    <div class="status warning">Moderate</div>
  </div>

  <div class="card">
    <h2>Air Quality (AQI)</h2>
    <div class="value" id="air">68</div>
    <div class="status good">Good</div>
  </div>

  <div class="card alert">
    🚨 ALERT<br>
    Heatwave expected in Central Zone (40 min)
  </div>

</div>

<!-- Temperature Trend Chart -->
<div class="chart-container">
  <h2>Temperature Trend</h2>
  <canvas id="tempChart"></canvas>
</div>

<!-- Air Quality Trend Chart -->
<div class="chart-container">
  <h2>Air Quality Trend</h2>
  <canvas id="airChart"></canvas>
</div>


<footer>
  Smart City • Real-Time Monitoring • AI Ready
</footer>

<script>
  // Utility
  function random(min, max) {
    return Math.floor(Math.random() * (max - min + 1)) + min;
  }

  // Trend Data Arrays
  let tempData = [];
  let airData  = [];
  let labels   = [];

  // Chart.js Temperature Trend
  const tempChart = new Chart(document.getElementById("tempChart"), {
    type: "line",
    data: {
      labels: labels,
      datasets: [{
        label: "Temperature (°C)",
        data: tempData,
        borderWidth: 3
      }]
    }
  });

  // Chart.js Air Quality Trend
  const airChart = new Chart(document.getElementById("airChart"), {
    type: "line",
    data: {
      labels: labels,
      datasets: [{
        label: "Air Quality (AQI)",
        data: airData,
        borderWidth: 3
      }]
    }
  });

  // Update all values every 3 seconds
  function updateDashboard() {
    // Live values
    let hum = random(40, 90);
    let temp = random(20, 40);
    let aqi = random(50, 150);

    document.getElementById("humidity").innerText = hum + "%";
    document.getElementById("temperature").innerText = temp + "°C";
    document.getElementById("air").innerText = aqi;

    // Trend labels
    let time = new Date().toLocaleTimeString();
    labels.push(time);
    if (labels.length > 10) labels.shift();

    // Push trend data
    tempData.push(temp);
    airData.push(aqi);
    if (tempData.length > 10) tempData.shift();
    if (airData.length > 10) airData.shift();

    // Update charts
    tempChart.update();
    airChart.update();
  }

  setInterval(updateDashboard, 3000);
</script>

</body>
</html>
