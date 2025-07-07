<script>
  import "../app.css";
</script>

<header>
  <h1>Odemy</h1>
  <button>Entrar</button>
</header>
<main>
  <p class="intro">A solução completa para ser um profissional de sucesso</p>
  <p class="intro2">
    Tenha técnicas impecáveis, finalize trabalhos rapidamente e domine o mercado
    de profissionais na sua região com ajuda dos nossos conteúdos exclusivos
    para assinantes.
  </p>
  <div class="mega">
    <div class="mini">
      <img
        src="https://www.tpdplay.com/storage/images/lp/hero-courses.webp"
        alt=""
      />
      <img
        src="https://www.tpdplay.com/storage/images/lp/hero-community.webp"
        alt=""
      />
    </div>
    <img src="https://www.tpdplay.com/storage/images/lp/hero-tpd.webp" alt="" />
    <div class="mini">
      <img
        src="https://www.tpdplay.com/storage/images/lp/hero-lessons.webp"
        alt=""
      />
      <img
        src="https://www.tpdplay.com/storage/images/lp/hero-virtual-assistant.webp"
        alt=""
      />
    </div>
  </div>
  <iframe
    width="800"
    height="450"
    src="https://www.youtube.com/embed/5Zmc6f420rg"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen
  >
  </iframe>

  <section class="finish">
    <div class="grup">
      <p>
        + de 7 cursos completos Da prótese total ao digital: todas as técnicas
        para fazer você ser o melhor.
      </p>
      <img
        src="https://www.tpdplay.com/storage/images/lp/7-cursos-completos.webp?v=1.0.0"
        alt=""
      />
    </div>
    <div class="grup">
      <p>
        Aula nova todo mês Nosso acervo de aulas está sempre sendo ampliado com
        o que há de mais atual no mundo da prótese
      </p>
      <img
        src="https://www.tpdplay.com/storage/images/lp/aula-nova-todo-mes.webp?v=1.0.0"
        alt=""
      />
    </div>
    <div class="grup">
      <p>
        Inteligência artificial Com nosso vasto sistema de busca, a informação
        que você precisa estará sempre na palma da sua mão.
      </p>
      <img
        src="https://www.tpdplay.com/storage/images/lp/inteligencia-artificial.webp?v=1.0.0"
        alt=""
      />
    </div>
    <div class="grup">
      <p>
        Pesquisa avançada Seus problemas resolvidos em apenas um clique. Seremos
        o seu Google da prótese. Não importa a sua dúvida, aqui você encontrará
        a resposta.
      </p>
      <img
        src="https://www.tpdplay.com/storage/images/lp/pesquisa-avancada.webp?v=1.0.0"
        alt=""
      />
    </div>
    <div class="grup">
      <p>
        Qualidade de cinema Aulas filmadas em 4K, onde todos os detalhes podem
        ser vistos e retomados conforme necessário, tendo um aproveitamento
        superior ao de um curso presencial.
      </p>
      <img
        src="https://www.tpdplay.com/storage/images/lp/qualidade-de-cinema.webp?v=1.0.0"
        alt=""
      />
    </div>
  </section>
  <button>Entre agora mesmo.</button>
</main>

<style>
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 2rem;
    background: rgba(0, 5, 20, 0.6);
    backdrop-filter: blur(10px);
    box-shadow: 0 4px 30px rgba(0, 10, 80, 0.3);
    position: sticky;
    top: 0;
    z-index: 100;
    border-bottom: 1px solid rgba(64, 128, 255, 0.2);
    animation: fadeInDown 0.8s ease-out;
  }

  h1 {
    font-size: clamp(1.8rem, 5vw, 2.8rem);
    font-weight: 800;
    background: linear-gradient(45deg, #a0d1ff, #5a9cff);
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    letter-spacing: -0.5px;
    text-shadow: 0 2px 8px rgba(90, 156, 255, 0.2);
    transition: all 0.4s ease;
  }

  h1:hover {
    text-shadow: 0 4px 15px rgba(90, 156, 255, 0.4);
    transform: scale(1.02);
  }

  button {
    background: linear-gradient(135deg, #1e40af, #2563eb);
    border: none;
    font-size: clamp(1rem, 1.5vw, 1.2rem);
    border-radius: 8px;
    padding: 0.6rem 1.8rem;
    user-select: none;
    cursor: pointer;
    transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    color: white;
    font-weight: 600;
    box-shadow: 0 4px 15px rgba(37, 99, 235, 0.3);
    position: relative;
    overflow: hidden;
  }

  button::after {
    content: "";
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(
      90deg,
      transparent,
      rgba(255, 255, 255, 0.2),
      transparent
    );
    transition: 0.6s;
  }

  button:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 25px rgba(37, 99, 235, 0.5);
  }

  button:hover::after {
    left: 100%;
  }

  button:active {
    transform: translateY(1px);
    box-shadow: 0 2px 10px rgba(37, 99, 235, 0.4);
  }

  main {
    padding: 2rem 5% 5rem;
    max-width: 1600px;
    margin: 0 auto;
  }

  .intro {
    max-width: 900px;
    width: 90%;
    text-align: center;
    margin: 3rem auto 0;
    font-size: clamp(2rem, 6vw, 3.8rem);
    font-weight: 800;
    line-height: 1.15;
    text-shadow: 0 2px 10px rgba(0, 80, 200, 0.4);
    background: linear-gradient(to right, #e0f0ff, #a0d1ff);
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    animation: fadeInUp 0.8s ease-out 0.2s both;
  }

  .intro2 {
    max-width: 900px;
    width: 90%;
    text-align: center;
    margin: 1.5rem auto 3rem;
    font-size: clamp(1.1rem, 3vw, 1.9rem);
    color: #c2e0ff;
    font-weight: 400;
    opacity: 0.9;
    animation: fadeInUp 0.8s ease-out 0.4s both;
  }

  .mega {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    gap: 1.5rem;
    margin: 4rem auto;
    perspective: 1200px;
    position: relative;
    z-index: 2;
  }

  .mega::before {
    content: "";
    position: absolute;
    top: -50px;
    left: -50px;
    right: -50px;
    bottom: -50px;
    background-image: url("https://images.unsplash.com/photo-1555066931-4365d14bab8c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=200&q=80"),
      url("https://images.unsplash.com/photo-1551650975-87deedd944c3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=200&q=80"),
      url("https://images.unsplash.com/photo-1542831371-29b0f74f9713?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=200&q=80"),
      url("https://images.unsplash.com/photo-1542831371-29b0f74f9713?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=200&q=80");
    background-position:
      10% 20%,
      90% 40%,
      30% 80%,
      70% 60%;
    background-repeat: no-repeat;
    background-size: 150px;
    opacity: 0.2;
    z-index: -1;
    animation: floatBackground 25s infinite linear;
  }

  @keyframes floatBackground {
    0% {
      background-position:
        10% 20%,
        90% 40%,
        30% 80%,
        70% 60%;
    }
    50% {
      background-position:
        15% 30%,
        85% 50%,
        35% 90%,
        65% 70%;
    }
    100% {
      background-position:
        10% 20%,
        90% 40%,
        30% 80%,
        70% 60%;
    }
  }

  .mini {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    user-select: none;
  }
  .mega img {
    user-select: none;
    max-width: 100%;
    height: auto;
    border-radius: 8px;
    object-fit: cover;
    transition: all 0.4s ease-out;
    opacity: 0.9;
  }

  .mega > img {
    width: min(630px, 90%);
    aspect-ratio: 16/9;
  }

  .mini img {
    width: min(180px, 25vw);
    aspect-ratio: 1/1;
  }

  .mega img:hover {
    opacity: 1;
    transform: translateY(-5px);
  }

  iframe {
    width: min(800px, 90%);
    border-radius: 16px;
    display: block;
    margin: 5rem auto;
    box-shadow:
      0 20px 50px rgba(0, 20, 100, 0.7),
      0 0 0 2px rgba(64, 128, 255, 0.2);
    transition:
      transform 0.4s,
      box-shadow 0.4s;
    animation: fadeIn 1s ease-out 0.6s both;
  }

  video:hover {
    transform: scale(1.02);
    box-shadow:
      0 25px 60px rgba(0, 30, 120, 0.8),
      0 0 20px rgba(64, 128, 255, 0.4);
  }

  .finish {
    display: flex;
    flex-direction: column;
    gap: 4rem;
    max-width: 1200px;
    margin: 6rem auto;
    user-select: none;
  }

  /* Layout coluna com texto à esquerda e imagem à direita */
  .grup {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    background: rgba(10, 20, 50, 0.4);
    border-radius: 16px;
    overflow: hidden;
    box-shadow:
      0 10px 30px rgba(0, 15, 50, 0.4),
      inset 0 0 0 1px rgba(64, 128, 255, 0.1);
    transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
    animation: fadeIn 0.6s ease-out forwards;
    animation-delay: calc(var(--delay) * 0.1s);
  }

  .grup:hover {
    transform: translateY(-8px);
    box-shadow:
      0 15px 40px rgba(0, 30, 100, 0.6),
      inset 0 0 0 1px rgba(100, 180, 255, 0.3);
    background: rgba(15, 30, 70, 0.5);
  }

  .grup p {
    padding: 2.5rem;
    font-size: clamp(1.1rem, 1.8vw, 1.3rem);
    color: #e0f0ff;
    line-height: 1.7;
    flex: 1;
    min-width: 300px;
  }

  .grup img {
    width: 45%;
    height: 300px;
    object-fit: cover;
    flex: 1;
    min-width: 300px;
    user-select: none;
  }

  /* Texto à esquerda, imagem à direita */
  .grup:nth-child(odd) {
    flex-direction: row;
  }

  /* Imagem à esquerda, texto à direita */
  .grup:nth-child(even) {
    flex-direction: row-reverse;
  }

  /* Placeholders para as imagens */
  .grup:nth-child(1) img {
    background: linear-gradient(45deg, #0a1429, #1a3b6d);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #5a9cff;
    font-size: 2rem;
    font-weight: bold;
    content: "Conteúdo Exclusivo";
  }

  .grup:nth-child(2) img {
    background: linear-gradient(45deg, #0a1429, #1a3b6d);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #5a9cff;
    font-size: 2rem;
    font-weight: bold;
    content: "Mentoria Personalizada";
  }

  .grup:nth-child(3) img {
    background: linear-gradient(45deg, #0a1429, #1a3b6d);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #5a9cff;
    font-size: 2rem;
    font-weight: bold;
    content: "Comunidade Ativa";
  }

  .grup:nth-child(4) img {
    background: linear-gradient(45deg, #0a1429, #1a3b6d);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #5a9cff;
    font-size: 2rem;
    font-weight: bold;
    content: "Atualizações Constantes";
  }

  .grup:nth-child(5) img {
    background: linear-gradient(45deg, #0a1429, #1a3b6d);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #5a9cff;
    font-size: 2rem;
    font-weight: bold;
    content: "Ferramentas Profissionais";
  }

  .grup:nth-child(6) img {
    background: linear-gradient(45deg, #0a1429, #1a3b6d);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #5a9cff;
    font-size: 2rem;
    font-weight: bold;
    content: "Suporte 24/7";
  }

  .grup:nth-child(7) img {
    background: linear-gradient(45deg, #0a1429, #1a3b6d);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #5a9cff;
    font-size: 2rem;
    font-weight: bold;
    content: "Certificação";
  }

  .grup:nth-child(8) img {
    background: linear-gradient(45deg, #0a1429, #1a3b6d);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #5a9cff;
    font-size: 2rem;
    font-weight: bold;
    content: "Networking";
  }

  .grup:nth-child(9) img {
    background: linear-gradient(45deg, #0a1429, #1a3b6d);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #5a9cff;
    font-size: 2rem;
    font-weight: bold;
    content: "Portfólio";
  }

  .grup:nth-child(10) img {
    background: linear-gradient(45deg, #0a1429, #1a3b6d);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #5a9cff;
    font-size: 2rem;
    font-weight: bold;
    content: "Carreira";
  }

  main > button:last-child {
    display: block;
    margin: 4rem auto 0;
    padding: 1.2rem 3.5rem;
    font-size: clamp(1.2rem, 2vw, 1.5rem);
    background: linear-gradient(135deg, #3b82f6, #1d4ed8);
    box-shadow: 0 10px 30px rgba(59, 130, 246, 0.4);
    animation: pulse 2s infinite;
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(40px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes fadeInDown {
    from {
      opacity: 0;
      transform: translateY(-40px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes float {
    0%,
    100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-15px);
    }
  }

  @keyframes pulse {
    0% {
      transform: scale(1);
      box-shadow: 0 0 0 0 rgba(59, 130, 246, 0.7);
    }
    70% {
      transform: scale(1.02);
      box-shadow: 0 0 0 15px rgba(59, 130, 246, 0);
    }
    100% {
      transform: scale(1);
      box-shadow: 0 0 0 0 rgba(59, 130, 246, 0);
    }
  }
  @media (max-width: 1157px) {
    .mini {
      display: none !important;
    }
  }
  @media (max-width: 900px) {
    .mega {
      flex-direction: column;
    }

    .grup {
      flex-direction: column !important;
    }

    .grup img {
      width: 100%;
      height: 250px;
    }
  }

  @media (max-width: 600px) {
    header {
      padding: 1rem;
    }

    video {
      margin: 3rem auto;
    }
  }

  @media (max-width: 480px) {
    .mega > img {
      order: -1;
    }

    button {
      padding: 0.5rem 1.2rem;
    }

    .intro,
    .intro2 {
      width: 95%;
    }

    .grup p,
    .grup img {
      min-width: 100%;
    }
  }
</style>
