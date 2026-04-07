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
    background: rgba(0,0,0,0.6);
    padding: 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

header h1 {
    color: #00c3ff;
}

nav a {
    color: white;
    margin: 0 10px;
    text-decoration: none;
}

.hero {
    text-align: center;
    padding: 100px 20px;
}

.hero h2 {
    font-size: 50px;
    color: #00c3ff;
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

.voos {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
}

.card {
    background: rgba(255,255,255,0.1);
    padding: 20px;
    border-radius: 10px;
    width: 250px;
}

footer {
    text-align: center;
    padding: 20px;
    background: #000;
}
</style>

</head>
<body>

<header>
    <h1>✈️ SKRDREAM</h1>
    <nav>
        <a href="#">Início</a>
        <a href="#voos">Voos</a>
        <a href="#sobre">Sobre</a>
    </nav>
</header>

<section class="hero">
    <h2>Viaje para qualquer lugar do mundo</h2>
    <p>Conforto, segurança e os melhores preços</p>
    <button onclick="mostrarVoos()">Ver voos</button>
</section>

<section id="voos" class="section">
    <h2>🌍 Voos Disponíveis</h2>
    <div class="voos">

        <div class="card">
            <h3>São Paulo → Rio</h3>
            <p>R$ 199</p>
            <button onclick="comprar()">Comprar</button>
        </div>

        <div class="card">
            <h3>Curitiba → São Paulo</h3>
            <p>R$ 150</p>
            <button onclick="comprar()">Comprar</button>
        </div>

        <div class="card">
            <h3>Brasil → EUA</h3>
            <p>R$ 2.500</p>
            <button onclick="comprar()">Comprar</button>
        </div>

        <div class="card">
            <h3>Brasil → Europa</h3>
            <p>R$ 3.200</p>
            <button onclick="comprar()">Comprar</button>
        </div>

    </div>
</section>

<section id="sobre" class="section">
    <h2>Sobre a SKRDREAM</h2>
    <p>
        A SKRDREAM é uma companhia aérea focada em oferecer a melhor experiência
        para seus passageiros. Nosso objetivo é conectar você ao mundo com conforto,
        segurança e tecnologia.
    </p>
</section>

<footer>
    <p>© 2026 SKRDREAM Airlines</p>
</footer>

<script>
function comprar() {
    alert("Compra realizada com sucesso! ✈️");
}

function mostrarVoos() {
    document.getElementById("voos").scrollIntoView({ behavior: "smooth" });
}
</script>

</body>
</html>
