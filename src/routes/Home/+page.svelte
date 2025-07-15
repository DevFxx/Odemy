<script>
  import "../../app.css";
  import { goto } from "$app/navigation";
  import { onMount, onDestroy } from "svelte";
  // Funções
  function voltar() {
    goto("../");
  }

  function toggleFAQ(index) {
    openIndex = openIndex === index ? null : index;
  }

  function next() {
    if (currentIndex < iframes.length - visibleCount) {
      currentIndex += 1;
    }
  }

  function prev() {
    if (currentIndex > 0) {
      currentIndex -= 1;
    }
  }

  // Dados estáticos
  const CURSO_EXEMPLO = {
    tituloBanner: "Curso de Python Avançado",
    gradient: "linear-gradient(45deg, #2c3e50, #4a6491)",
    desconto: 30,
    titulo: "Python para Ciência de Dados",
    descricao:
      "Domine Python, Pandas, NumPy e Matplotlib para análise e visualização de dados. Aprenda técnicas avançadas de machine learning.",
    autor: "Luiz Inácio",
    autorInicial: "LI",
    avatarBg: "#3498db",
    nota: 4.7,
    preco: 200.88,
    precoOriginal: 287,
  };

  export let cursos = Array(6).fill({ ...CURSO_EXEMPLO });

  const faqs = [
    {
      question: "Quem somos?",
      answer: "O TPDPlay é uma plataforma de aulas por assinatura...",
    },
    {
      question: "Posso cancelar minha assinatura?",
      answer: "Sim, a qualquer momento na sua área de usuário.",
    },
    {
      question: "Preciso pagar taxa extra?",
      answer: "Não. Você paga só o valor da assinatura.",
    },
  ];

  const iframes = Array(19).fill("https://www.youtube.com/embed/dQw4w9WgXcQ");

  // Estados
  let players = [];
  let openIndex = null;
  let currentIndex = 0;
  const visibleCount = 5;
  const slideWidth = 300;
  let youtubeAPIReady = false;

  // Gerenciamento da API do YouTube
  onMount(() => {
    if (
      !document.querySelector(
        'script[src="https://www.youtube.com/iframe_api"]'
      )
    ) {
      const tag = document.createElement("script");
      tag.src = "https://www.youtube.com/iframe_api";
      document.head.appendChild(tag);
    }

    window.onYouTubeIframeAPIReady = initializePlayers;
  });

  function initializePlayers() {
    youtubeAPIReady = true;
    document.querySelectorAll(".yt-iframe").forEach((iframe, index) => {
      const player = new YT.Player(iframe);
      players[index] = player;

      const container = iframe.closest(".card-video");
      if (container) {
        container.addEventListener("mouseenter", () => player.playVideo());
        container.addEventListener("mouseleave", () => player.pauseVideo());
      }
    });
  }

  onDestroy(() => {
    players.forEach((player) => {
      try {
        player.destroy();
      } catch (e) {
        console.error("Error destroying player", e);
      }
    });
    players = [];
  });
</script>

<section class="main">
  <header>
    <h1>Odemy</h1>
    <nav>
      <ul>
        <li><a href="/faq"><i class="bi bi-book"></i> FAQ</a></li>
        <li><a href="/carrinho"><i class="bi bi-basket3"></i> Carrinho</a></li>
        <li><a href="/buscar"><i class="bi bi-search"></i> Procurar</a></li>
        <li><a href="/contato"><i class="bi bi-telephone"></i> Contato</a></li>
      </ul>
    </nav>
  </header>

  <p class="intro">Conheça a Odemy</p>
  <iframe
  class="video"
    width="1000"
    height="800"
    src="https://www.youtube.com/embed/yMEBbrPpjhA?si=V9RW9Pw1LKgHEmqW"
    title="YouTube video player"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    referrerpolicy="strict-origin-when-cross-origin"
    allowfullscreen
  ></iframe>

  <p class="introCurso">Nossos cursos</p>
  <div class="cards-container">
    {#each cursos as curso, index}
      <article class="card">
        <div class="card-header">
          <div class="card-video" style="background: {curso.gradient}">
            <iframe
              class="yt-iframe"
              width="100%"
              height="100%"
              src="https://www.youtube.com/embed/wFIR32vN12I?enablejsapi=1"
              title="YouTube video player"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
              referrerpolicy="strict-origin-when-cross-origin"
              allowfullscreen
            ></iframe>
          </div>
          {#if curso.desconto}
            <div class="discount-badge">-{curso.desconto}%</div>
          {/if}
        </div>
        <div class="card-content">
          <h3 class="card-title">{curso.titulo}</h3>
          <p class="card-description">{curso.descricao}</p>
          <div class="card-author">
            <div
              class="author-avatar"
              style="background: {curso.avatarBg}"
              aria-label="Avatar de {curso.autor}"
            >
              {curso.autorInicial}
            </div>
            <span>{curso.autor}</span>
          </div>
          <div class="rating">
            <div class="stars">
              {#each Array(5)
                .fill(0)
                .map( (_, i) => (i < Math.floor(curso.nota) ? "fas fa-star" : i < curso.nota ? "fas fa-star-half-alt" : "far fa-star") ) as icon}
                <i class={icon}></i>
              {/each}
            </div>
            <span class="rating-value">{curso.nota.toFixed(1)}</span>
          </div>
          <div class="price-container">
            <div>
              <span class="price">R$ {curso.preco.toFixed(2)}</span><br />
              {#if curso.precoOriginal}
                <span class="original-price"
                  >R$ {curso.precoOriginal.toFixed(2)}</span
                >
              {/if}
            </div>
            <div class="actions">
              <button class="buy-btn"
                ><i class="fas fa-shopping-bag"></i> Comprar</button
              >
              <button class="cart-btn"><i class="bi bi-basket3"></i></button>
            </div>
          </div>
        </div>
      </article>
    {/each}
  </div>
  <section class="planos">
    <h2>Escolha seu Plano</h2>
    <div class="planos-container">
      <div class="plano">
        <h3>Semestral</h3>
        <p class="preco">R$ 199,90</p>

        <button class="btn-assinar">Assinar</button>
      </div>

      <div class="plano destaque">
        <h3>Vitalício</h3>
        <p class="preco">R$ 899,90</p>

        <button class="btn-assinar">Assinar</button>
      </div>
      <div class="plano">
        <h3>Anual</h3>
        <p class="preco">R$ 349,90</p>

        <button class="btn-assinar">Assinar</button>
      </div>
    </div>
  </section>
  <h2 class="intro2">Vidas que já transformamos</h2>
  <div class="carousel">
    <div
      class="slides"
      style="transform: translateX({-currentIndex * (slideWidth + 10)}px)"
    >
      {#each iframes as url, i (i)}
        <iframe
          src={url}
          allowfullscreen
          class="feed"
          loading="lazy"
          title={`Vídeo ${i + 1}`}
        ></iframe>
      {/each}
    </div>

    <button
      class="prev"
      on:click={prev}
      disabled={currentIndex === 0}
      aria-label="Vídeos anteriores"
    >
      <i class="bi bi-arrow-left-circle"></i>
    </button>
    <button
      class="next"
      on:click={next}
      disabled={currentIndex >= iframes.length - visibleCount}
      aria-label="Próximos vídeos"
    >
      <i class="bi bi-arrow-right-circle"></i>
    </button>
  </div>
  <div class="faq-container">
    <h2>Dúvidas? Dê uma olhada aqui.</h2>
    <p>
      Não encontrou uma resposta? Entre em contato com nosso suporte e ficaremos
      felizes em te ajudar!
    </p>
    {#each faqs as faq, index (index)}
      <div class="faq-item" class:open={openIndex === index}>
        <button
          class="faq-question"
          on:click={() => toggleFAQ(index)}
          aria-expanded={openIndex === index}
          aria-controls={`faq-answer-${index}`}
        >
          {faq.question}
        </button>

        <div
          id={`faq-answer-${index}`}
          class="faq-answer"
          role="region"
          aria-hidden={openIndex !== index}
        >
          <p>{faq.answer}</p>
        </div>
      </div>
    {/each}
  </div>
  <footer>
    <div class="footer-container">
      <div class="footer-contact">
        <a href="#"><i class="bi bi-whatsapp"></i> (99) 9999-9999</a>
        <a href="#"><i class="bi bi-envelope-at"></i> Exemple@gmail.com</a>
      </div>
      <p>&copy; 2025 Odemy. Todos os direitos reservados.</p>
    </div>
  </footer>
</section>

<style>
  .carousel {
    position: relative;
    width: 100%; /* 3 * 300px */
    overflow: hidden;
    margin: 0 auto;
    margin-bottom: 5rem;
  }

  .slides {
    display: flex;
    transition: transform 0.5s ease;
    width: max-content;
  }

  .feed {
    border-radius: 8px;
    border: none;
    width: 450px;
    height: 200px;
    margin-right: 10px;
  }

  .prev,
  .next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    color: #2563eb;
    font-size: 5rem;
    background: transparent;
    text-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
    border: none;
    cursor: pointer;
    padding: 0.5rem 1rem;
    z-index: 1;
  }

  .prev {
    left: 10px;
  }

  .next {
    right: 10px;
  }
  .faq-container {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
    font-family: "Arial", sans-serif;
  }
  .faq-container h2,
  .faq-container p {
    text-align: center;
  }
  .faq-container p {
    font-size: 1.2rem;
  }
  .faq-container h2 {
    font-size: 3rem;
  }

  .faq-item {
    border-bottom: 1px solid #e0e0e0;
    margin-bottom: 10px;
  }

  .faq-question {
    width: 100%;
    text-align: left;
    padding: 15px 0 15px 40px;
    font-size: 1.1rem;
    font-weight: 600;
    background: none;
    border: none;
    cursor: pointer;
    position: relative;
    display: block;
    color: white;
  }

  /* Ícone + e - */
  .faq-question:before {
    content: "+";
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 30px;
    height: 30px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.5rem;
    font-weight: normal;
    background: transparent;
    border-radius: 50%;
    transition: all 0.3s ease;
  }

  .faq-item.open .faq-question:before {
    content: "−";
    background: transparent;
  }

  .faq-answer {
    max-height: 0;
    opacity: 0;
    transition:
      max-height 0.3s ease,
      opacity 0.3s ease,
      padding 0.3s ease;
    padding-left: 40px;
  }

  .faq-item.open .faq-answer {
    max-height: 900px;
    opacity: 1;
    padding-bottom: 15px;
  }

  .faq-answer p {
    margin: 0;
    line-height: 1.6;
    color: #dedede;
    padding: 5px 0;
  }

  footer {
    background-color: rgba(0, 0, 0, 0.2); /* cor de fundo escura */
    color: #fff; /* texto branco */
    padding: 2rem 1rem;
    text-align: center;
    font-size: 1.4rem;
    letter-spacing: 2px;
  }
  footer a {
    letter-spacing: 0;
  }

  .footer-container {
    width: 100vw;
    margin: 0 auto;
  }

  .footer-contact {
    margin-bottom: 1rem;
  }

  .footer-contact a {
    color: #fff;
    text-decoration: none;
    margin: 0 1rem;
    font-weight: bold;
    transition: color 0.3s;
  }

  .footer-contact a:hover {
    color: #5a9cff; /* cor ao passar o mouse */
  }

  @media (max-width: 600px) {
    .footer-contact a {
      display: block;
      margin: 0.5rem 0;
    }
  }

  .planos {
    text-align: center;
    padding: 3rem 1rem;
    background: transparent;
    color: #fff;
  }

  .planos h2,
  .intro2 {
    font-size: 3rem;
    margin-bottom: 2rem;
  }

  .planos-container {
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
    justify-content: center;
  }

  .plano {
    background: transparent;
    border-radius: 12px;
    padding: 2rem;
    width: 280px;
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
    transition:
      transform 0.3s ease,
      box-shadow 0.3s ease;
  }

  .plano:hover {
    transform: translateY(-8px);
    box-shadow: 0 12px 30px rgba(0, 0, 0, 0.2);
  }

  .plano h3 {
    font-size: 1.5rem;
    margin-bottom: 0.5rem;
    color: #fff;
  }

  .plano .preco {
    font-size: 1.8rem;
    font-weight: bold;
    color: #fff;
    margin-bottom: 1rem;
  }

  .plano ul {
    list-style: none;
    padding: 0;
    margin: 0 0 1.5rem 0;
    text-align: left;
  }

  .plano ul li {
    margin-bottom: 0.5rem;
    position: relative;
    padding-left: 1.5rem;
  }

  .plano ul li::before {
    content: "✔";
    position: absolute;
    left: 0;
    color: #10b981;
    font-weight: bold;
  }

  .btn-assinar {
    background: #2563eb;
    color: white;
    border: none;
    padding: 0.8rem 1.5rem;
    border-radius: 8px;
    cursor: pointer;
    font-weight: bold;
    transition: background 0.3s ease;
  }

  .btn-assinar:hover {
    background: #1d4ed8;
  }

  .plano.destaque {
    border: 2px solid #2563eb;
    transform: scale(1.05);
  }

  @media (max-width: 768px) {
    .planos-container {
      flex-direction: column;
      align-items: center;
    }
  }
  /* Usa o teu mesmo CSS, só mantive o essencial do card-video */

  .main {
    width: 100%;
    min-height: 100vh;
    position: relative;
    background: transparent;
    background: url("/background.jpeg") center/cover no-repeat;
    display: flex;
    flex-direction: column;
    align-items: center;
    box-sizing: border-box;
  }

  /* header, nav, intro, video, cards-container etc... igual ao teu */

  .card-video {
    width: 100%;
    height: 200px;
    overflow: hidden;
  }

  iframe {
    border: none;
    display: block;
    transition: 0.6s;
  }
  iframe:hover {
  }

  .main {
    width: 100%;
    min-height: 100vh;
    position: relative;
    color: white;
    background: url("/background.jpeg") center/cover no-repeat;
    display: flex;
    flex-direction: column;
    align-items: center;
    box-sizing: border-box;
  }

  header {
    position: absolute;
    left: 0;
    top: 0;
    right: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    background: rgba(0, 5, 20, 0.6);
    backdrop-filter: blur(10px);
    box-shadow: 0 4px 30px rgba(0, 10, 80, 0.3);
    z-index: 100;
  }

  nav ul {
    display: flex;
    gap: 1rem;
    list-style-type: none;
  }

  nav a {
    display: flex;
    align-items: center;
    gap: 0.3rem;
    background: linear-gradient(135deg, #1e40af, #2563eb);
    padding: 0.4rem 0.8rem;
    border-radius: 8px;
    box-shadow: 0 4px 15px rgba(37, 99, 235, 0.3);
    text-decoration: none;
    color: white;
    font-weight: 600;
    transition:
      transform 0.2s,
      box-shadow 0.2s;
  }

  nav a:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 25px rgba(37, 99, 235, 0.5);
  }
  h1 {
    user-select: none;
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

  .intro,
  .introCurso {
    max-width: 800px;
    width: 90%;
    margin: 1rem auto;
    text-align: center;
    font-size: 1.8rem;
    color: #a0d1ff;
    background-color: rgba(0, 0, 0, 0.2);
    padding: 1rem;
    border-radius: 8px;
    letter-spacing: 1px;
  }


  .cards-container {
    width: 1500px;
    max-width: 100%;
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    align-items: center;
    justify-content: center;
    margin: 0 auto;
  }

  /* Mantém o CSS dos cards igual ao original */

  .card {
    background: #051446;
    border-radius: 15px;
    width: 400px;
    max-width: 400px;
    overflow: hidden;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
    transition:
      transform 0.3s ease,
      box-shadow 0.3s ease;
  }

  .card:hover {
    transform: translateY(-10px);
    box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
  }

  .card-header {
    position: relative;
  }

  .card-video {
    width: 100%;
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 1.5rem;
    font-weight: bold;
  }

  .play-icon {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 3rem;
    color: rgba(255, 255, 255, 0.8);
    text-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  }

  .card-content {
    padding: 20px;
  }

  .card-title {
    font-size: 1.4rem;
    font-weight: 700;
    margin-bottom: 10px;
    color: #ffffff;
  }

  .card-description {
    color: #808080;
    font-size: 0.95rem;
    margin-bottom: 15px;
    line-height: 1.5;
    min-height: 70px;
  }

  .card-author {
    display: flex;
    align-items: center;
    margin-bottom: 15px;
    color: #ffffff;
  }

  .author-avatar {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-weight: bold;
    margin-right: 10px;
  }

  .rating {
    display: flex;
    align-items: center;
    margin-bottom: 15px;
  }

  .stars {
    color: #f39c12;
    margin-right: 10px;
  }

  .rating-value {
    background: #f1c40f;
    color: white;
    font-weight: bold;
    padding: 3px 8px;
    border-radius: 20px;
    font-size: 0.9rem;
  }

  .price-container {
    display: flex;
    justify-content: space-between;
    align-items: center;

    margin-top: 15px;
    padding-top: 15px;
    border-top: 1px solid #eee;
  }

  .price {
    font-size: 1.8rem;
    font-weight: bold;
    color: #e74c3c;
  }

  .original-price {
    text-decoration: line-through;
    color: #95a5a6;
    font-size: 1.1rem;
    margin-left: 5px;
  }

  .actions {
    display: flex;
    gap: 10px;
  }

  .buy-btn,
  .cart-btn {
    border: none;
    padding: 10px 15px;
    border-radius: 5px;
    cursor: pointer;
    font-weight: 600;
    font-size: 1.6rem;
    transition: all 0.3s ease;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .buy-btn {
    background: #27ae60;
    color: white;
  }

  .buy-btn:hover {
    background: #219653;
    transform: scale(1.05);
  }

  .cart-btn {
    background: #3498db;
    color: white;
  }

  .cart-btn:hover {
    background: #2980b9;
    transform: scale(1.05);
  }

  .discount-badge {
    position: absolute;
    top: 15px;
    right: 15px;
    background: #e74c3c;
    color: white;
    padding: 5px 10px;
    border-radius: 20px;
    font-weight: bold;
    font-size: 0.9rem;
  }

  .footer {
    width: 100%;
    text-align: center;
    padding: 1.5rem 0;
    background: rgba(0, 5, 20, 0.6);
    backdrop-filter: blur(10px);
  }
  .feed:hover {
    transform: scale(1);
  }
  .video{
    width: 1000px;
    height: 500px;
    border-radius: 8px;
  }
  .video:hover{
    transform: scale(1);
  }
  .card-video {
    overflow: visible;
    transition: all 0.4s ease;
    position: relative;
    z-index: 1;
  }

  .card-video iframe {
    transition: transform 0.4s ease;
    transform-origin: center;
  }

  .card-video:hover iframe {
    transform: scale(1.15);
    z-index: 10;
    box-shadow: 0 0 30px rgba(0, 0, 0, 0.5);
  }

  .video:hover {
    transform: scale(1) !important;
  }
</style>
