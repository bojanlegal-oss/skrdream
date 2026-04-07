<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SKRDREAM Airlines</title>

<style>
body {
    margin: 0;
    font-family: Arial;
    background: linear-gradient(135deg, #0b0f1a, #001f3f);
    color: white;
}

header {
    background: rgba(0,0,0,0.7);
    padding: 15px;
    text-align: center;
}

header h1 {
    color: #00c3ff;
    margin: 0;
}

.hero {
    text-align: center;
    padding: 100px 20px;
}

.hero h2 {
    font-size: 45px;
    color: #00c3ff;
}

.hero p {
    font-size: 18px;
}

button {
    padding: 12px 25px;
    font-size: 16px;
    background: #00c3ff;
    border: none;
    border-radius: 8px;
    cursor: pointer;
}

button:hover {
    background: #0099cc;
}

.section {
    padding: 50px;
    text-align: center;
}

.card {
    background: rgba(255,255,255,0.1);
    padding: 25px;
    border-radius: 12px;
    width: 280px;
    margin: auto;
    box-shadow: 0 0 15px rgba(0,195,255,0.3);
}

.price {
    color: #00c3ff;
    font-size: 24px;
    margin: 15px 0;
}

footer {
    text-align: center;
    padding: 20px;
    background: #000;
    margin-top: 50px;
}
</style>
</head>

<body>

<header>
    <h1>✈️ SKRDREAM Airlines</h1>
</header>

<section class="hero">
    <h2>Viaje para Miami com conforto</h2>
    <p>A melhor experiência aérea com tudo incluso</p>
    <button onclick="irParaVoos()">Ver voo</button>
</section>

<section id="voos" class="section">
    <h2>🌍 Voo Disponível</h2>

    <div class="card">
        <h3>Brasil → Miami 🇺🇸</h3>
        <p><strong>Classe Econômica Premium</strong></p>
        <p>✔ Bagagem inclusa</p>
        <p>✔ Refeições completas</p>
        <p>✔ Entretenimento a bordo</p>
        <p>✔ Assento confortável</p>

        <div class="price">
            R$ 3.499 (tudo incluso)
        </div>

        <button onclick="comprar()">Comprar passagem</button>
    </div>
</section>

<footer>
    <p>© 2026 SKRDREAM Airlines - Todos os direitos reservados</p>
</footer>

<script>
function comprar() {
    alert("✈️ Passagem para Miami comprada com sucesso!");
}

function irParaVoos() {
    document.getElementById("voos").scrollIntoView({ behavior: "smooth" });
}
</script>

</body>
</html>
