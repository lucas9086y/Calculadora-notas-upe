# Calculadora-notas-upe.  
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Calculadora de Notas UPE</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f2f2f2;
      padding: 20px;
    }
    h1 {
      color: #2c3e50;
      text-align: center;
    }
    .container {
      background: #fff;
      border-radius: 8px;
      max-width: 600px;
      margin: auto;
      padding: 20px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    .unidade {
      margin-bottom: 30px;
    }
    label {
      display: block;
      margin: 10px 0 5px;
    }
    input[type="number"] {
      width: 100%;
      padding: 8px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
    button {
      margin-top: 15px;
      padding: 10px 20px;
      background: #3498db;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }
    button:hover {
      background: #2980b9;
    }
    .resultado {
      margin-top: 20px;
      font-size: 1.2em;
      font-weight: bold;
    }
  </style>
</head>
<body>

<div class="container">
  <h1>Calculadora de Notas - UPE</h1>

  <div class="unidade" id="unidade1">
    <h2>Unidade 1</h2>
    <label>Fórum 1 (máx 1.0):</label>
    <input type="number" id="forum1" step="0.1" min="0" max="1">
    <label>WQ1 (máx 2.5):</label>
    <input type="number" id="wq1" step="0.1" min="0" max="2.5">
    <label>Prova 1 (máx 5.5):</label>
    <input type="number" id="prova1" step="0.1" min="0" max="5.5">
    <label>Fórum 2 (máx 1.0):</label>
    <input type="number" id="forum2" step="0.1" min="0" max="1">
  </div>

  <div class="unidade" id="unidade2">
    <h2>Unidade 2</h2>
    <label>Fórum 3 (máx 1.0):</label>
    <input type="number" id="forum3" step="0.1" min="0" max="1">
    <label>WQ2 (máx 2.5):</label>
    <input type="number" id="wq2" step="0.1" min="0" max="2.5">
    <label>Prova 2 (máx 5.5):</label>
    <input type="number" id="prova2" step="0.1" min="0" max="5.5">
    <label>Fórum 4 (máx 1.0):</label>
    <input type="number" id="forum4" step="0.1" min="0" max="1">
  </div>

  <button onclick="calcularNotas()">Calcular</button>

  <div class="resultado" id="resultado"></div>
</div>

<script>
  function calcularNotas() {
    // Unidade 1
    let forum1 = parseFloat(document.getElementById('forum1').value) || 0;
    let wq1 = parseFloat(document.getElementById('wq1').value) || 0;
    let prova1 = parseFloat(document.getElementById('prova1').value) || 0;
    let forum2 = parseFloat(document.getElementById('forum2').value) || 0;
    let total1 = forum1 + wq1 + prova1 + forum2;
    let status1 = total1 >= 6 ? "✅ Aprovado" : "❌ Reprovado";

    // Unidade 2
    let forum3 = parseFloat(document.getElementById('forum3').value) || 0;
    let wq2 = parseFloat(document.getElementById('wq2').value) || 0;
    let prova2 = parseFloat(document.getElementById('prova2').value) || 0;
    let forum4 = parseFloat(document.getElementById('forum4').value) || 0;
    let total2 = forum3 + wq2 + prova2 + forum4;
    let status2 = total2 >= 6 ? "✅ Aprovado" : "❌ Reprovado";

    let mediaFinal = (total1 + total2) / 2;
    let statusFinal = mediaFinal >= 6 ? "✅ Aprovado Geral" : "❌ Reprovado Geral";

    document.getElementById("resultado").innerHTML = `
      <p><strong>Unidade 1:</strong> ${total1.toFixed(2)} pontos → ${status1}</p>
      <p><strong>Unidade 2:</strong> ${total2.toFixed(2)} pontos → ${status2}</p>
      <p><strong>Média Final:</strong> ${mediaFinal.toFixed(2)} pontos → ${statusFinal}</p>
    `;
  }
</script>

</body>
</html>
