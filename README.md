<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SkyHigh Master - Sistema de Viagens</title>
    <style>
        :root { --p: #003366; --s: #38bdf8; --a: #ffcc00; --bg: #f1f5f9; }
        body { font-family: sans-serif; background: var(--bg); margin: 0; color: #1e293b; }
        header { background: var(--p); color: white; padding: 15px 30px; display: flex; justify-content: space-between; align-items: center; position: sticky; top: 0; z-index: 100; }
        nav button { background: none; border: none; color: white; font-weight: bold; cursor: pointer; padding: 10px; }
        .btn-res { background: var(--a) !important; color: var(--p) !important; border-radius: 5px; }
        .container { padding: 30px; max-width: 1100px; margin: auto; }
        .aba { display: none; background: white; padding: 30px; border-radius: 15px; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
        .active { display: block; }
        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 20px; margin-top: 20px; }
        .card { border: 1px solid #ddd; border-radius: 10px; overflow: hidden; }
        .card img { width: 100%; height: 180px; object-fit: cover; }
        .card-body { padding: 15px; }
        /* Mapa Assentos */
        .mapa { display: grid; grid-template-columns: repeat(4, 1fr); gap: 10px; max-width: 250px; margin: 20px auto; }
        .poltrona { width: 45px; height: 45px; background: #ddd; border-radius: 5px; cursor: pointer; display: flex; align-items: center; justify-content: center; }
        .selecionada { background: var(--s); color: white; }
        .ocupada { background: #bbb; cursor: not-allowed; opacity: 0.5; }
        /* Tabela */
        table { width: 100%; border-collapse: collapse; margin-top: 20px; }
        th, td { padding: 12px; text-align: left; border-bottom: 1px solid #eee; }
        th { background: var(--p); color: white; }
        .input-full { width: 100%; padding: 12px; margin: 10px 0; border: 1px solid #ccc; border-radius: 5px; box-sizing: border-box; }
    </style>
</head>
<body>

<header>
    <h2 style="margin:0;">SKYHIGH ✈️</h2>
    <nav>
        <button onclick="ver('h')">HOME</button>
        <button onclick="ver('p')">HOTÉIS</button>
        <button onclick="ver('r')">ROTEIRO</button>
        <button onclick="ver('a')">ASSENTOS</button>
        <button onclick="ver('c')" class="btn-res">CHECKOUT</button>
    </nav>
</header>

<div class="container">
    <div id="aba-h" class="aba active">
        <h1>Dashboard do Viajante</h1>
        <div class="grid">
            <div style="background:var(--p); color:white; padding:20px; border-radius:10px;">
                <h3>Voo Confirmado</h3>
                <p>GRU ➔ MIA | Voo SH-202</p>
                <small>Bagagem: 2x 23kg inclusas</small>
            </div>
            <div style="background:#dcfce7; padding:20px; border-radius:10px; border:1px solid #22c55e;">
                <h3>Seguro Viagem</h3>
                <p>Status: <b>Ativo</b></p>
                <p>Cobertura: $1.000.000 (Platinum)</p>
            </div>
        </div>
    </div>

    <div id="aba-p" class="aba">
        <h2>Hospedagem All-Inclusive</h2>
        <div class="grid">
            <div class="card">
                <img src="https://images.unsplash.com/photo-1520250497591-112f2f40a3f4?w=400">
                <div class="card-body"><h4>Miami Luxury Palace</h4><p>Resort 5 estrelas com tudo incluso.</p></div>
            </div>
            <div class="card">
                <img src="https://images.unsplash.com/photo-1582719478250-c89cae4dc85b?w=400">
                <div class="card-body"><h4>South Beach Suites</h4><p>Vista mar e serviço de concierge.</p></div>
            </div>
        </div>
    </div>

    <div id="aba-r" class="aba">
        <h2>Roteiro de 7 Dias</h2>
        <table>
            <tr><th>Dia</th><th>Atividade</th><th>Refeição</th></tr>
            <tr><td>1</td><td>Chegada e Transfer VIP</td><td>Jantar Boas-vindas</td></tr>
            <tr><td>2</td><td>Passeio de Iate Privado</td><td>Almoço no Mar</td></tr>
            <tr><td>3</td><td>Compras e Outlets</td><td>Livre</td></tr>
            <tr><td>4-7</td><td>Praia e Everglades</td><td>Incluso no Hotel</td></tr>
        </table>
    </div>

    <div id="aba-a" class="aba">
        <h2 style="text-align:center;">Selecione sua Poltrona</h2>
        <div class="mapa" id="grid-assento"></div>
        <p style="text-align:center;">Selecionado: <b id="seat-val">01A</b></p>
    </div>

    <div id="aba-c" class="aba">
        <div id="form-pag">
            <h2 style="text-align:center;">Finalizar Pacote Master</h2>
            <div style="background:#f8fafc; padding:20px; border-radius:10px; text-align:center; border:2px dashed var(--s);">
                <p style="margin:0;">TOTAL TUDO INCLUSO</p>
                <h1 style="margin:5px 0; color:var(--p);">R$ 8.450,00</h1>
            </div>
            <input type="text" id="user-nome" class="input-full" placeholder="Nome Completo do Passageiro">
            <button onclick="finalizar()" style="width:100%; padding:15px; background:var(--p); color:white; border:none; border-radius:5px; font-weight:bold; cursor:pointer; margin-top:10px;">CONFIRMAR RESERVA</button>
        </div>

        <div id="sucesso" style="display:none; text-align:center;">
            <h1 style="color:#22c55e;">✅ RESERVA EMITIDA!</h1>
            <div style="border:2px solid #000; padding:20px; display:inline-block; text-align:left; background:white;">
                <h3>VOUCHER SKYHIGH</h3>
                <p>NOME: <span id="res-nome"></span></p>
                <p>ASSENTO: <span id="res-seat"></span></p>
                <p>VOO: SH-202 | MIA</p>
                <img src="https://api.qrserver.com/v1/create-qr-code/?size=100x100&data=SkyHigh" style="display:block; margin:auto;">
            </div>
        </div>
    </div>
</div>

<script>
    let assentoSel = "01A";
    function ver(id) {
        document.querySelectorAll('.aba').forEach(a => a.classList.remove('active'));
        document.getElementById('aba-' + id).classList.add('active');
    }

    // Criar mapa de assentos
    const grid = document.getElementById('grid-assento');
    for(let i=1; i<=5; i++) {
        ['A','B','C','D'].forEach(letra => {
            const div = document.createElement('div');
            div.className = 'poltrona';
            div.innerText = i + letra;
            div.onclick = function() {
                document.querySelectorAll('.poltrona').forEach(p => p.classList.remove('selecionada'));
                div.classList.add('selecionada');
                assentoSel = div.innerText;
                document.getElementById('seat-val').innerText = assentoSel;
            };
            grid.appendChild(div);
        });
    }

    function finalizar() {
        const n = document.getElementById('user-nome').value;
        if(n.length > 3) {
            document.getElementById('form-pag').style.display = 'none';
            document.getElementById('sucesso').style.display = 'block';
            document.getElementById('res-nome').innerText = n.toUpperCase();
            document.getElementById('res-seat').innerText = assentoSel;
        } else {
            alert("Digite o nome completo!");
        }
    }
</script>

</body>
</html>
