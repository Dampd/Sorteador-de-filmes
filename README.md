<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>CineSorteio 🎬</title>
    <style>
        body { font-family: sans-serif; text-align: center; padding: 20px; background: #141414; color: white; }
        textarea { width: 90%; height: 100px; margin-bottom: 10px; }
        button { padding: 10px 20px; cursor: pointer; background: red; color: white; border: none; }
        #resultado { margin-top: 20px; font-size: 24px; color: gold; font-weight: bold; }
    </style>
</head>
<body>
    <h1>CineSorteio</h1>
    <textarea id="lista" placeholder="Digite um filme por linha..."></textarea><br>
    <button onclick="sortear()">SORTEAR</button>
    <div id="resultado">Aguardando sorteio...</div>

    <script>
        function sortear() {
            const txt = document.getElementById('lista').value;
            const filmes = txt.split('\n').filter(f => f.trim() !== "");
            if (filmes.length === 0) {
                alert("Sua lista está vazia!");
                return;
            }
            const sorteado = filmes[Math.floor(Math.random() * filmes.length)];
            document.getElementById('resultado').innerText = "🎬 " + sorteado;
        }
    </script>
</body>
</html>
