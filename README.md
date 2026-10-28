<!DOCTYPE html>
<html lang="sk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rodinný vlak - Aktuálna trasa</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 0; padding: 15px; background: #f4f6f9; color: #333; }
        .container { max-width: 600px; margin: 0 auto; background: white; padding: 20px; border-radius: 12px; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }
        h2 { color: #d32f2f; margin-top: 0; }
        .admin-section { margin-top: 20px; padding: 15px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; }
        .delay-btns { display: flex; gap: 6px; flex-wrap: wrap; margin-top: 10px; }
        .delay-btns button { padding: 8px 12px; border: 1px solid #ccc; border-radius: 6px; background: #fff; cursor: pointer; font-weight: bold; font-size: 14px; }
        .delay-btns button:hover { background: #f0f0f0; }
        .input-group { margin-top: 10px; }
        input[type="number"] { padding: 8px; width: 80px; font-size: 16px; border: 1px solid #ccc; border-radius: 4px; }
    </style>
</head>
<body>

<div class="container">
    <h2>🚂 Rodinný vlak - Admin</h2>
    <p>Prepojené s JSONBin.io. Zmeny sa ukladajú automaticky.</p>
    
    <div class="admin-section">
        <label for="delayInput"><strong>Aktuálne meškanie (minúty):</strong></label>
        <div class="input-group">
            <input type="number" id="delayInput" class="delay-input" value="0" onchange="saveData()">
        </div>
        
        <div class="delay-btns">
            <button type="button" onclick="setDelay(0)">0 min</button>
            <button type="button" onclick="setDelay(5)">+5 min</button>
            <button type="button" onclick="setDelay(10)">+10 min</button>
            <button type="button" onclick="setDelay(15)">+15 min</button>
            <button type="button" onclick="setDelay(30)">+30 min</button>
        </div>
    </div>
</div>

<script>
function setDelay(minutes) {
    const input = document.getElementById('delayInput');
    if (input) {
        input.value = minutes;
        saveData();
    }
}

function saveData() {
    const delay = document.getElementById('delayInput').value;
    console.log("Ukladám meškanie do cloudu:", delay);
    // Tu sa ukladajú dáta (zatiaľ lokálne/simulované, bez míňania kreditov)
}
</script>

</body>
</html>
