<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Pet Virtual</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <header class="header">
            <h1>Meu Pet Virtual</h1>
        </header>
        <div class="content">
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam et felis ac nisi facilisis facilisis.</p>
            <img src="https://br.freepik.com/fotos-premium/um-monstro-de-desenho-animado-com-uma-cabeca-espetada-e-uma-cabeca-espetada-senta-se-em-uma-mesa_45576247.htm" alt="Imagem do Pet" id="petImage">
            <p>Saciedade: <span id="hunger">100</span></p>
            <p id="message">Interaja com o seu pet.</p>
        </div>
        <button id="feedButton">Alimentar</button>
        <button id="bathButton">Dar Banho</button>
        <button id="playButton">Brincar</button>
    </div>

    <script src="script.js"></script>
</body>
</html>

.container {
    text-align: center;
    margin: 20px;
}

.header {
    background-color: #f2f2f2;
    padding: 10px;
}

.content {
    margin-top: 20px;
}

button {
    margin: 10px;
    padding: 5px 10px;
    background-color: #4CAF50;
    color: white;
    border: none;
    cursor: pointer;
}
button:hover {
    background-color: #45a049;
}

let saturationLevel = 100;

function updateSaturationLevel(value) {
    saturationLevel += value;
    if (saturationLevel > 100) {
        saturationLevel = 100;
    } else if (saturationLevel < 0) {
        saturationLevel = 0;
    }
    document.getElementById('hunger').textContent = saturationLevel;
}

function feedPet() {
    updateSaturationLevel(20);
    document.getElementById('message').textContent = "Pet foi alimentado.";
}

function bathPet() {
    updateSaturationLevel(10);
    document.getElementById('message').textContent = "Pet tomou banho.";
}

function playPet() {
    updateSaturationLevel(-10);
    document.getElementById('message').textContent = "Pet brincou e sua saciedade diminuiu.";
}
