<!DOCTYPE html>
<html>
<head><meta name="google-site-verification" content="al_st2jLJ9GJc_ChXFbvwU8kFGNF0MlcWUfMZN5jDms" />
<title>Degree Calculator</title>
<style>
  body { font-family: Arial; text-align: center; background: #f0f0f0; padding: 20px; }
  .box { background: white; padding: 20px; border-radius: 15px; max-width: 400px; margin: auto; box-shadow: 0 0 10px gray; }
  input { width: 80%; padding: 12px; font-size: 20px; text-align: center; border: 2px solid #4CAF50; border-radius: 10px; }
  button { background: #4CAF50; color: white; padding: 12px 25px; font-size: 18px; border: none; border-radius: 10px; margin-top: 15px; cursor: pointer; }
  .result { text-align: left; margin-top: 20px; font-size: 18px; background: #e8f5e9; padding: 15px; border-radius: 10px; }
  b { color: #2e7d32; }
</style>
</head>
<body>

<div class="box">
  <h2>🔥 Degree Calculator 🔥</h2>
  <p>Decimal number dalo jaise 0.5735</p>
  <input type="number" id="num" step="any" placeholder="Ex: 0.5735" value="0.5735">
  <br>
  <button onclick="calculate()">Degree Nikalo</button>
  <div class="result" id="out">Yaha answer aayega...</div>
</div>

<script>
function calculate() {
  let x = parseFloat(document.getElementById("num").value);
  if (isNaN(x)) { document.getElementById("out").innerHTML = "Pehle number to dal bhai!"; return; }

  let r = "";
  let toDeg = (rad) => (rad * 180 / Math.PI).toFixed(2);

  // sin inverse
  if (x >= -1 && x <= 1) r += `<b>sin<sup>-1</sup>(${x})</b> = ${toDeg(Math.asin(x))}°<br><br>`;
  else r += `<b>sin<sup>-1</sup>(${x})</b> = Nahi hoga (-1 se 1 ke beech dal)<br><br>`;

  // cos inverse
  if (x >= -1 && x <= 1) r += `<b>cos<sup>-1</sup>(${x})</b> = ${toDeg(Math.acos(x))}°<br><br>`;
  else r += `<b>cos<sup>-1</sup>(${x})</b> = Nahi hoga<br><br>`;

  // tan inverse
  r += `<b>tan<sup>-1</sup>(${x})</b> = ${toDeg(Math.atan(x))}°<br><br>`;

  // cot inverse
  if (x != 0) r += `<b>cot<sup>-1</sup>(${x})</b> = ${toDeg(Math.atan(1/x))}°<br><br>`;
  else r += `<b>cot<sup>-1</sup>(0)</b> = 90.00°<br><br>`;

  // sec inverse
  if (x != 0 && (1/x) >= -1 && (1/x) <= 1) r += `<b>sec<sup>-1</sup>(${x})</b> = ${toDeg(Math.acos(1/x))}°<br><br>`;
  else r += `<b>sec<sup>-1</sup>(${x})</b> = Nahi hoga (1 se bada dal)<br><br>`;

  // cosec inverse
  if (x != 0 && (1/x) >= -1 && (1/x) <= 1) r += `<b>cosec<sup>-1</sup>(${x})</b> = ${toDeg(Math.asin(1/x))}°<br><br>`;
  else r += `<b>cosec<sup>-1</sup>(${x})</b> = Nahi hoga (1 se bada dal)<br><br>`;

  document.getElementById("out").innerHTML = r;
}
// Pehle se hi ek baar chala do
calculate();
</script>

</body>
</html>
