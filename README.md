<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Visor de Carta de Porte Digital - Amarintrans</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; background: #f4f6f9; color: #333; }
    .card { background: white; padding: 20px; max-width: 600px; margin: 0 auto; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1); }
    h1 { color: #1a365d; font-size: 18px; border-bottom: 2px solid #1a365d; padding-bottom: 8px; }
    .item { margin-bottom: 10px; }
    .label { font-weight: bold; color: #4a5568; }
  </style>
</head>
<body>

<div class="card">
  <h1>Carta de Porte Digital (DECA)</h1>
  <div id="contenido">Cargando datos...</div>
</div>

<script>
  const p = new URLSearchParams(window.location.search);
  
  if (p.has('ref')) {
    document.getElementById('contenido').innerHTML = `
      <div class="item"><span class="label">Referencia:</span> ${p.get('ref')}</div>
      <div class="item"><span class="label">Expedidor:</span> ${p.get('exp')} (${p.get('expCif')})</div>
      <div class="item"><span class="label">Origen:</span> ${p.get('expDir')}</div>
      <hr>
      <div class="item"><span class="label">Destinatario:</span> ${p.get('dest')} (${p.get('destCif')})</div>
      <div class="item"><span class="label">Destino:</span> ${p.get('destDir')}</div>
      <hr>
      <div class="item"><span class="label">Transportista:</span> ${p.get('trans')} (${p.get('transCif')})</div>
      <div class="item"><span class="label">Matrícula:</span> ${p.get('mat')} / ${p.get('rem')}</div>
      <hr>
      <div class="item"><span class="label">Mercancía:</span> ${p.get('prod')}</div>
      <div class="item"><span class="label">Peso:</span> ${p.get('kg')} kg</div>
    `;
  } else {
    document.getElementById('contenido').innerText = "No se ha proporcionado ninguna referencia válida.";
  }
</script>

</body>
</html>
