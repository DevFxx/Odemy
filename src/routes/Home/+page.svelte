<script>
  import "../../app.css";
  import { goto } from "$app/navigation";
  function voltar() {
    goto("../");
  }
</script>

<section class="main">
  <header>
    <h1>Odemy</h1>
    <nav>
      <ul>
        <li><i class="bi bi-book"></i> FAQ</li>
        <li><i class="bi bi-basket3"></i> Carrinho</li>
        <li><i class="bi bi-search"></i> Procurar</li>
        <li><i class="bi bi-telephone"></i> Contato</li>
      </ul>
    </nav>
  </header>
</section>

<style>
  li,
  nav,
  ul {
    background: transparent;
  }
  ul {
    list-style-type: none;
    gap: 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-direction: row;
  }
  i {
    background: transparent;
    color: black;
    font-size: 1rem;
    color: white;
    font-weight: 600;
  }
  li {
    transition: 0.2s;
    cursor: pointer;
    border-radius: 6px;
    background: linear-gradient(135deg, #1e40af, #2563eb);
    border: none;
    font-size: clamp(1rem, 1.5vw, 1rem);
    border-radius: 8px;
    padding: 0.2rem 0.4rem;
    user-select: none;
    cursor: pointer;
    transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    color: white;
    font-weight: 600;
    box-shadow: 0 4px 15px rgba(37, 99, 235, 0.3);
    position: relative;
    overflow: hidden;
    letter-spacing: 1px;
  }
  li:hover {
    transform: scale(1.05) translateY(-3px);
    box-shadow: 0 5px 4px rgba(0, 5, 20, 0.6);
  }
  li::after {
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

  li:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 25px rgba(37, 99, 235, 0.5);
  }

  li:hover::after {
    left: 100%;
  }

  li:active {
    transform: translateY(1px);
    box-shadow: 0 2px 10px rgba(37, 99, 235, 0.4);
  }
  .nav {
    background: transparent;
  }
  .main {
    width: 100vw;
    height: 100vh;
    box-sizing: border-box;
    background-image: url("/background.jpeg");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 2rem;
    background: rgba(0, 5, 20, 0.6);
    backdrop-filter: blur(10px);
    box-shadow: 0 4px 30px rgba(0, 10, 80, 0.3);
    position: relative;
    top: 0;
    left: 0;
    right: 0;
    z-index: 100;
    border-bottom: 1px solid rgba(64, 128, 255, 0.2);
    animation: fadeInDown 0.8s ease-out;
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
    letter-spacing: 2px;
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

  #bg-video {
    position: fixed;
    top: 0;
    left: 0;
    min-width: 100%;
    min-height: 100%;
    z-index: -1;
    object-fit: cover;
  }
  .main {
    position: relative;
    z-index: 1;
    color: white;
  }
</style>
