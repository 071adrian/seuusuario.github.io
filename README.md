<!DOCTYPE html><html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Crie seu Personagem - Demon Slayer</title>
  <style>
    body {
      background: url('https://i.imgur.com/zl0vLr1.jpeg') no-repeat center center fixed;
      background-size: cover;
      font-family: 'Arial', sans-serif;
      color: #fff;
      text-align: center;
      padding: 20px;
    }
    h1 {
      font-size: 2.5em;
      margin-bottom: 10px;
      background-color: rgba(0,0,0,0.6);
      display: inline-block;
      padding: 10px 20px;
      border-radius: 12px;
    }
    button {
      margin: 10px;
      padding: 12px 20px;
      font-size: 16px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      background-color: #f39c12;
      color: white;
    }
    #resultado {
      margin-top: 20px;
      background-color: rgba(0,0,0,0.7);
      padding: 20px;
      border-radius: 12px;
    }
    .atributo {
      font-size: 1.3em;
      margin-bottom: 10px;
    }
  </style>
</head>
<body>
  <h1>🎴 Crie seu Personagem - Demon Slayer 🎴</h1>
  <div>
    <button onclick="sortearPersonagem()">Gerar Personagem</button>
    <button onclick="compartilharPersonagem()">Compartilhar</button>
  </div>  <div id="resultado"></div>  <script>
    const racas = ["Humano", "Oni"];

    const humano = {
      respiracoes: ["Água", "Chama", "Som", "Névoa", "Inseto", "Vento", "Pedra", "Fera", "Amor", "Serpente"],
      ranks: ["Mizunoto", "Mizunoe", "Kanoto", "Kanone", "Tsuchinoto", "Tsuchinoe", "Hashira"],
      armas: ["Nichirin tradicional", "Nichirin dupla", "Foice", "Corrente", "Arco com lâminas"],
      personalidade: ["Calmo", "Explosivo", "Justo", "Vingativo", "Protetor"],
      historia: ["Família morta por Onis", "Treinado por ex-Hashira", "Sobrevivente de vila destruída", "Perdeu irmão para Muzan"],
      caracteristicas: ["Cabelos coloridos", "Olhos diferentes", "Cicatriz marcante", "Marca de caçador"],
      forca: [
        "Derrubaria um Oni com um golpe só",
        "Conseguiria lutar contra uma Lua Superior",
        "Poder equilibrado e técnico",
        "Precisa de ajuda para lutar com Onis medianos",
        "Está começando sua jornada, mas tem potencial"
      ]
    };

    const oni = {
      poder: ["Regeneração absurda", "Manipulação de sombras", "Explosão de sangue", "Controle de ossos", "Manipulação sonora"],
      posicao: ["Sem posição", "Lua Inferior", "Lua Superior"],
      fraqueza: ["Luz solar intensa", "Nichirin vermelha", "Baixa resistência", "Lento em combate", "Instável mentalmente"],
      personalidade: ["Cruel", "Sádico", "Solitário", "Arrogante", "Calculista"],
      historia: ["Transformado por Muzan", "Traído por humanos", "Busca redenção", "Era caçador antes de virar Oni"],
      aparencia: ["Chifres", "Pele escura com marcas", "Olhos brilhantes e vermelhos", "Garras longas", "Forma monstruosa"],
      forca: [
        "Destruiria uma vila sozinho",
        "Enfrentaria 3 caçadores ao mesmo tempo",
        "Rápido e letal",
        "Só luta à noite e se esconde de Hashiras",
        "É fraco, mas esperto"
      ]
    };

    function sortear(array) {
      return array[Math.floor(Math.random() * array.length)];
    }

    function sortearPersonagem() {
      const resultado = document.getElementById("resultado");
      resultado.innerHTML = "";
      const raca = sortear(racas);

      let texto = `<div class='atributo'><strong>Raça:</strong> ${raca}</div>`;

      if (raca === "Humano") {
        texto += `
          <div class='atributo'><strong>Respiração:</strong> ${sortear(humano.respiracoes)}</div>
          <div class='atributo'><strong>Rank:</strong> ${sortear(humano.ranks)}</div>
          <div class='atributo'><strong>Arma:</strong> ${sortear(humano.armas)}</div>
          <div class='atributo'><strong>Personalidade:</strong> ${sortear(humano.personalidade)}</div>
          <div class='atributo'><strong>História:</strong> ${sortear(humano.historia)}</div>
          <div class='atributo'><strong>Características Físicas:</strong> ${sortear(humano.caracteristicas)}</div>
          <div class='atributo'><strong>Nível de Força:</strong> ${sortear(humano.forca)}</div>
        `;
      } else {
        texto += `
          <div class='atributo'><strong>Poder Demoníaco:</strong> ${sortear(oni.poder)}</div>
          <div class='atributo'><strong>Posição:</strong> ${sortear(oni.posicao)}</div>
          <div class='atributo'><strong>Fraqueza:</strong> ${sortear(oni.fraqueza)}</div>
          <div class='atributo'><strong>Personalidade:</strong> ${sortear(oni.personality)}</div>
          <div class='atributo'><strong>História:</strong> ${sortear(oni.historia)}</div>
          <div class='atributo'><strong>Aparência Demoníaca:</strong> ${sortear(oni.aparencia)}</div>
          <div class='atributo'><strong>Nível de Força:</strong> ${sortear(oni.forca)}</div>
        `;
      }

      resultado.innerHTML = texto;
    }

    function compartilharPersonagem() {
      const texto = document.getElementById("resultado").innerText;
      navigator.clipboard.writeText(texto).then(() => {
        alert("Personagem copiado para a área de transferência! Cole onde quiser compartilhar.");
      });
    }
  </script></body>
</html>
