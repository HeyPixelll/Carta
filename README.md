<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Carta Romântica com Botões</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: white; /* Fundo branco */
      font-family: 'Georgia', serif; /* Fonte mais romântica */
    }

    /* Estilo da carta */
    .carta {
      position: relative;
      width: 270px;  /* Ajuste o tamanho da carta */
      height: 210px; /* Ajuste a altura da carta */
      background-color: #f9c5c8; /* Cor rosa */
      border-radius: 10px;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      font-size: 14px; /* Diminui mais o tamanho da fonte */
      color: #333;
      transition: background-color 0.3s ease;
      padding: 12px; /* Ajuste o padding */
      flex-direction: column;
      overflow: hidden; /* Impede o conteúdo de sair da carta */
    }

    /* Corações espalhados ao redor da carta */
    .carta::before, .carta::after, .carta .coração-esquerda, .carta .coração-direita {
      content: '❤️';
      position: absolute;
      font-size: 18px;
      color: #ff4d4d; /* Cor dos corações */
    }

    .carta::before {
      top: -20px;
      left: 50%;
      transform: translateX(-50%);
    }

    .carta::after {
      bottom: -20px;
      left: 50%;
      transform: translateX(-50%);
    }

    .carta .coração-esquerda {
      top: 50%;
      left: -15px;
      transform: translateY(-50%);
    }

    .carta .coração-direita {
      top: 50%;
      right: -15px;
      transform: translateY(-50%);
    }

    /* Mensagem escondida inicialmente */
    .mensagem {
      display: none;
      font-size: 12px; /* Reduz ainda mais o tamanho da fonte */
      color: #333;
      text-align: center;
      opacity: 0;
      transition: opacity 0.5s ease;
      padding: 8px;
    }

    /* Mostrar a mensagem quando a carta está ativa */
    .carta.ativa .mensagem {
      display: block;
      opacity: 1;
    }

    .carta.ativa {
      background-color: #ffb6c1; /* Cor rosa mais clara ao abrir */
    }

    /* Esconde o texto inicial quando a carta é aberta */
    .carta p.texto-inicial {
      margin: 0;
      font-size: 12px; /* Ajuste o tamanho da fonte */
      color: #555;
      transition: opacity 0.3s ease;
      font-weight: bold; /* Negrito */
    }

    .carta.ativa p.texto-inicial {
      opacity: 0;
    }

    /* Estilo dos botões */
    .botoes {
      margin-top: 12px; /* Reduz o espaço entre a carta e os botões */
      display: flex;
      gap: 8px; /* Espaço entre os botões */
    }

    .botoes button {
      padding: 6px 12px; /* Ajuste no tamanho do botão */
      font-size: 12px; /* Reduz o tamanho da fonte dos botões */
      border: none;
      border-radius: 5px;
      background-color: #ff4d4d; /* Cor vermelha */
      color: white;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    .botoes button:hover {
      background-color: #ff1a1a; /* Cor vermelha mais escura ao passar o mouse */
    }

    /* Mensagem extra (inicialmente escondida) */
    .mensagem-extra {
      font-size: 12px; /* Ajuste o tamanho da fonte */
      color: #d9534f;
      text-align: center;
      margin-top: 8px; /* Ajuste a margem */
      font-weight: bold;
      display: none;
      opacity: 0;
      transition: opacity 0.5s ease;
    }

    /* Exibe a mensagem extra quando a carta está ativa */
    .carta.ativa + .mensagem-extra {
      display: block;
      opacity: 1;
    }
  </style>
</head>
<body>
  <!-- Mensagem antes da carta -->
  <div class="carta">
    <p class="texto-inicial">Para Minha larinhaalinda</p>
    
    <div class="mensagem">
      <p>
        Minha Larinhaaa, meu amorzinho...<br><br>
        Você foi única a realmente entender meus sentimentos e a corresponder a cada um deles de um jeito tão lindinho sendo gentil e tudo que você é. Eu gosto muito, muito, muito, muito de você mais do que as palavras podem expressar. Você não faz ideia do quanto seu carinho melhora meus dias e do quanto sou grato por ter você ao meu ladinho.<br><br>
        Você é a melhor coisinha dos meus dias, o meu abrigo, a minha felicidade... ❤️
      </p>
    </div>
  </div>

  <!-- Frase que aparece somente depois de abrir a carta -->
  <p class="mensagem-extra">Você é a melhor parte da minha vida! ❤️</p>

  <div class="botoes">
    <button onclick="abrirCarta()">Abrir</button>
    <button onclick="resetarCarta()">Resetar</button>
  </div>

  <script>
    const carta = document.querySelector('.carta');
    const mensagemExtra = document.querySelector('.mensagem-extra');

    function abrirCarta() {
      carta.classList.add('ativa');
      mensagemExtra.style.display = 'block'; // Mostra a frase
      setTimeout(() => {
        mensagemExtra.style.opacity = '1'; // Faz a frase aparecer suavemente
      }, 100);
    }

    function resetarCarta() {
      carta.classList.remove('ativa');
      mensagemExtra.style.opacity = '0'; // Esconde a frase suavemente
      setTimeout(() => {
        mensagemExtra.style.display = 'none'; // Remove a frase depois de esconder
      }, 500);
    }
  </script>
</body>
</html>
