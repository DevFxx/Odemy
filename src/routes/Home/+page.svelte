<script>
  import "../../app.css";
  import { goto } from "$app/navigation";

  function voltar() {
    goto("../");
  }

  // dados de exemplo
  export let cursos = [
    {
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
    },
    {
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
    },
    {
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
    },
    {
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
    },
    {
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
    },
    {
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
    },
    // ... restante dos cursos (mantém o que já tens)
  ];

  let players = [];

  // Carregar API do YouTube
  let tag = document.createElement("script");
  tag.src = "https://www.youtube.com/iframe_api";
  let firstScriptTag = document.getElementsByTagName("script")[0];
  firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

  // Cria players quando API estiver pronta
  window.onYouTubeIframeAPIReady = () => {
    const iframes = document.querySelectorAll(".yt-iframe");
    iframes.forEach((iframe, index) => {
      const player = new YT.Player(iframe);
      players[index] = player;

      // Adiciona eventos de hover em cada container
      iframe.parentNode.addEventListener("mouseenter", () => {
        player.playVideo();
      });
      iframe.parentNode.addEventListener("mouseleave", () => {
        player.pauseVideo();
      });
    });
  };
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
  <video
    src="/videos/intro.mp4"
    controls
    poster="/videos/intro-poster.jpg"
    aria-label="Vídeo de apresentação da Odemy"
  >
    Seu navegador não suporta vídeo.
  </video>

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

  .planos h2 {
    font-size: 2rem;
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
    transition: .6s;
  }
  iframe:hover {
    transform: scale(1.1);
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

  video {
    width: 90%;
    max-width: 800px;
    height: auto;
    border-radius: 8px;
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
</style>
