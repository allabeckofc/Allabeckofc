<!DOCTYPE html><html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Você Conhece a Novinha?</title>
  <link href="https://fonts.googleapis.com/css2?family=Rubik:wght@400;700&family=Allura&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Rubik', sans-serif;
      background-color: #000;
      color: #fff;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      text-align: center;
      padding: 20px;
      position: relative;
    }
    h1 {
      font-size: 2.3rem;
      color: #ff004f;
      animation: pulse 2s infinite;
    }
    .delicate {
      font-family: 'Allura', cursive;
      font-size: 3.2rem;
      margin-bottom: 10px;
      color: #ff004f;
      transform: rotate(-3deg);
    }
    p {
      font-size: 1.1rem;
      margin: 20px 0;
    }
    .cta-button, .quiz-option {
      background-color: #ff004f;
      border: none;
      color: white;
      padding: 15px 30px;
      font-size: 1.1rem;
      cursor: pointer;
      border-radius: 10px;
      margin: 10px 0;
      box-shadow: 0 0 15px #ff004f;
    }
    .quiz-container, .preview-container, .idade-container, .foto-container, .delicia-container {
      display: none;
      flex-direction: column;
      gap: 15px;
      margin-top: 30px;
      align-items: center;
    }
    .quiz-question {
      font-size: 1rem;
    }
    .contador-fake {
      font-size: 0.9rem;
      color: #aaa;
      margin-top: 10px;
    }
    @keyframes pulse {
      0% { opacity: 1; }
      50% { opacity: 0.5; }
      100% { opacity: 1; }
    }
    img.preview {
      max-width: 300px;
      margin-top: 20px;
      border-radius: 15px;
      box-shadow: 0 0 20px #ff004f;
    }
    .comentarios-fake {
      margin-top: 30px;
      font-size: 0.95rem;
      color: #ccc;
      text-align: center;
      max-width: 320px;
      height: 60px;
      overflow: hidden;
      position: relative;
    }
    .comentario {
      opacity: 0;
      position: absolute;
      width: 100%;
      transition: opacity 0.5s;
    }
    .floating-preview {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background-color: #ff004f;
      color: white;
      padding: 12px;
      border-radius: 50%;
      font-size: 1.5rem;
      cursor: pointer;
      box-shadow: 0 0 15px #ff004f;
      z-index: 999;
    }
    .video-modal {
      display: none;
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: black;
      padding: 15px;
      border: 2px solid #ff004f;
      z-index: 1000;
    }
    .video-modal iframe {
      width: 300px;
      height: 530px;
    }
    .close-modal {
      background: none;
      color: #ff004f;
      font-size: 1rem;
      margin-top: 10px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <div id="tela1">
    <h1>ELA POSTA ISSO SÓ PRA QUEM PAGA…</h1>
    <p>Novinha polêmica do Insta agora tá vendendo fotos que não aparecem nem nos Close Friends.<br><strong>Quer ver o que ela manda no privado?</strong></p>
    <button class="cta-button" onclick="mostrarIdade()">VER UMA AMOSTRA DAS FOTOS</button>
  </div>  <div class="idade-container" id="tela2">
    <p>Você tem mais de 18 anos?</p>
    <button class="cta-button" onclick="mostrarPreview()">Sim, tenho +18</button>
    <button class="cta-button" onclick="alert('Essa página é restrita para maiores de 18 anos.');">Não</button>
  </div>  <div class="preview-container" id="tela3">
    <div class="delicate">Alla Beck</div>
    <img class="preview" src="https://i.imgur.com/MjRJ6C3.png" alt="Preview da Novinha">
    <button class="cta-button" onclick="mostrarQuiz()">VER MAIS FOTOS PRIVADAS</button>
  </div>  <div class="quiz-container" id="tela4">
    <div class="quiz-question">Você tá pronto pra ver o conteúdo que fez mais de 1000 marmanjos perderem a cabeça?</div>
    <div class="contador-fake">123 pessoas estão vendo agora...</div>
    <div class="quiz-option" onclick="mostrarDelicia()">Tô mais que pronto!</div>
    <div class="quiz-option" onclick="mostrarDelicia()">Manda logo essas fotos!</div>
  </div>  <div class="delicia-container" id="tela5">
    <h1>SE DELICIE NA PRÓXIMA TELA...</h1>
    <div class="comentarios-fake" id="comentarios">
      <div class="comentario">@marmanjo77: 🔥 Vi só 1 vídeo e já assinei o mês inteiro, é surreal!</div>
      <div class="comentario">@punheteirodigital: Mano… ela faz o que o Insta não deixa. Melhor investimento que já fiz.</div>
      <div class="comentario">@anonimoviciado: Pensei que era bait, mas o conteúdo é REALMENTE insano!</div>
    </div>
    <button class="cta-button" onclick="finalizar()">VER TUDO AGORA</button>
  </div>  <div class="floating-preview" onclick="abrirModal()">▶</div>
  <div class="video-modal" id="modalVideo">
    <iframe src="https://streamable.com/e/op5znb" frameborder="0" allowfullscreen></iframe>
    <button class="close-modal" onclick="fecharModal()">Fechar</button>
  </div>  <script>
    function mostrarIdade() {
      document.getElementById('tela1').style.display = 'none';
      document.getElementById('tela2').style.display = 'flex';
    }
    function mostrarPreview() {
      document.getElementById('tela2').style.display = 'none';
      document.getElementById('tela3').style.display = 'flex';
    }
    function mostrarQuiz() {
      document.getElementById('tela3').style.display = 'none';
      document.getElementById('tela4').style.display = 'flex';
    }
    function mostrarDelicia() {
      document.getElementById('tela4').style.display = 'none';
      document.getElementById('tela5').style.display = 'flex';
    }
    function finalizar() {
      window.location.href = 'https://global.tribopay.com.br/euvjpn69yf';
    }
    function abrirModal() {
      document.getElementById('modalVideo').style.display = 'block';
    }
    function fecharModal() {
      document.getElementById('modalVideo').style.display = 'none';
    }

    let currentComentario = 0;
    const comentarios = document.querySelectorAll('.comentario');
    if (comentarios.length > 0) {
      comentarios[0].style.opacity = 1;
      setInterval(() => {
        comentarios[currentComentario].style.opacity = 0;
        currentComentario = (currentComentario + 1) % comentarios.length;
        comentarios[currentComentario].style.opacity = 1;
      }, 3000);
    }
  </script></body>
</html>
