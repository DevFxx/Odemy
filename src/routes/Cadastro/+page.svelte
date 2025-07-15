<script>
  import "../../app.css";
  import { goto } from "$app/navigation";
  function voltar() {
    goto("../");
  }
  function test() {
    goto("../Home");
  }
</script>

<section class="main">
  <header>
    <h1>Odemy</h1>
    <button on:click={voltar}>Voltar</button>
  </header>
  <main>
    <form action="">
      <article class="grup">
        <label for="name">Nome completo</label>
        <input
          type="text"
          id="name"
          aria-required="true"
          required
          placeholder="Nome completo"
          minlength="3"
          maxlength="90"
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
          maxlength="90"
        />
      </article>
      <article class="grup">
        <label for="confirmpassword">Confirmar senha</label>
        <input
          type="password"
          id="confirmpassword"
          aria-required="true"
          required
          placeholder="repita a senha"
          minlength="8"
          maxlength="90"
        />
      </article>
      <article class="grup">
        <label for="email">E-mail</label>
        <input
          type="email"
          id="email"
          aria-required="true"
          required
          placeholder=" ex: Exemplo@gmail.com"
          minlength="5"
          maxlength="254"
        />
      </article>
      <article class="grup">
        <label for="date">Data de nascimento</label>
        <input type="date" id="date" aria-required="true" required />
      </article>
      <article class="grup">
        <label for="tel">Telefone</label>
        <input
          type="tel"
          id="tel"
          aria-required="true"
          required
          minlength="10"
          maxlength="15"
          placeholder="ex: (99) 99999-9999"
        />
      </article>
      <article class="grup">
        <label for="cpf">CPF</label>
        <input
          type="text"
          id="cpf"
          aria-required="true"
          required
          minlength="11"
          maxlength="14"
          placeholder="ex: 111.777.999-00"
        />
      </article>
      <button type="submit" on:click={test()}>Logar</button>
      <article class="as">
        <a href="#" on:click={voltar}>Já tem conta?</a>
      </article>
    </form>
  </main>
</section>

<style>
  .main {
    width: 100vw;
    height: 100vh;
    box-sizing: border-box;
  }
  main {
    background: transparent;
    padding: 2rem 0;
  }
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 2rem;
    background: rgba(0, 5, 20, 0.6);
    backdrop-filter: blur(10px);
    box-shadow: 0 4px 30px rgba(0, 10, 80, 0.3);
    position: sticky;
    top: 0;
    z-index: 100;
    border-bottom: 1px solid rgba(64, 128, 255, 0.2);
    animation: fadeInDown 0.8s ease-out;
    width: 100vw;
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
    height: auto;
    padding: 2rem 0;
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
    background: transparent;
    transition: all 0.2s;
  }
  .as a {
    color: white;
  }
  a {
    background: transparent;
  }
  .as a:hover {
    color: grey;
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
