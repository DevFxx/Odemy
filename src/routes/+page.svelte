<script>
  // import { GDK_BACKEND } from "./../../.svelte-kit/ambient.d.ts";
  import "../app.css";
  import { goto } from "$app/navigation";
  function voltar() {
    goto("../");
  }
  function account() {
    goto("../Cadastro");
  }
</script>


  <header>
    <h1>Odemy</h1>
    <button on:click={voltar}>Voltar</button>
  </header>
  <div class="video">
    <video src="" controls></video>
  </div>
  <form action="">
    <article class="grup">
      <label for="email">E-mail</label>
      <input
        type="email"
        id="email"
        aria-required="true"
        required
        placeholder="ex: Exemplo@gmail.com"
      />
    </article>
    <article class="grup">
      <label for="password">Senha</label>
      <input
        type="password"
        id="password"
        aria-required="true"
        required
        placeholder="ex: Senha123"
        minlength="8"
      />
    </article>
    <button type="submit">Logar</button>
    <article class="as" style="background: transparent;">
      <a>Esqueceu a senha?</a>
      <a href="#" on:click={account}>Não tem conta?</a>
    </article>
  </form>


<style>
  .video{
    width: 800px;
    height: 400px;
    margin: 0 auto;
    margin-top: 2rem;
  }
  video{
    width: 100%;
    height: auto;
    border-radius: 8px;
  }
  .main {
    width: 100vw;
    height:auto;
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
  form {
    background-color: rgba(0, 5, 20, 0.9);
    color: #fff;
    border-radius: 10px;
    height: 350px;
    width: 280px;
    margin: 0 auto;
    margin-top: 2rem;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 2rem;
    box-shadow:
      0 20px 50px rgba(0, 0, 0, 0.7),
      0 0 0 2px rgba(64, 128, 255, 0.2);
    transition: all 0.5s;
    margin-bottom: 2rem;
  }
  form:hover {
    transform: translateY(-2px);
  }
  .grup {
    display: flex;
    justify-content: center;
    flex-direction: column;
    gap: 5px;
    background: transparent;
  }
  label {
    font-size: 1.5rem;
    background: transparent;
  }
  input {
    padding: 0.4rem;
    border-radius: 4px;
    border: 1px white solid;
  }

  input:not(:placeholder-shown) {
    color: white;
  }
  .as {
    display: flex;
    gap: 10px;
    text-decoration: underline;
    user-select: none;
    cursor: pointer;
    transition: all 0.2s;
  }
  .as a {
    color: white;
    background: transparent;
  }
  .as a:hover {
    color: grey;
  }

</style>
