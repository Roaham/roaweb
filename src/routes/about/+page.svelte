<script>
  import { base } from '$app/paths';

  const profile = {
    name: "Roaham",
    bio: "Hola — soy Roaham. Me gusta la cyberseguridad, programar, la historia, leer y los videojueguitos",
    email: "hyperoa@proton.me",
    knowledge: [
      "Python: Intermedio (Análisis de datos, automatización y back-ends con Flask).",
      "Java: Intermedio (Programación orientada a objetos, fundamentos de Spring Boot y lógica de aplicaciones).",
      "CSS: Intermedio (Diseño responsivo, Flexbox, Grid y maquetación avanzada).",   
      "HTML: Intermedio (Marcado semántico, estructuras web y optimización básica de SEO).",
      "JavaScript: Principiante (Sintaxis fundamental, manipulación básica del DOM y conceptos básicos de ES6+).",
      "SQL: Principiante (Consultas básicas, diseño de tablas y manipulación de datos relacionales).",   
      "Svelte: Intermedio (Desarrollo de interfaces basadas en componentes y gestión de estado reactivo)."
    ]
  };

  const socialLinks = [
    { name: 'Discord', href: 'https://discord.gg/wtEhz63dYf', icon: '/discord.svg' },
    { name: 'X', href: 'https://x.com/GRorich10', icon: '/twitter.svg' },
    { name: 'Steam', href: 'https://steamcommunity.com/...', icon: '/steam.svg' },
    { name: 'Github', href: 'https://github.com/Roaham', icon: '/github.svg' }
  ];
</script>

<main class="shell">
  <header class="top-bar">
    <div class="url-bar">{profile.name.toLowerCase()}420.com</div>
    <nav class="nav-social">
      <ul class="social-list">
        {#each socialLinks as { name, href, icon }}
          <li>
            <a {href} target="_blank" rel="noopener noreferrer" class="social-btn">
              <img src="{base}{icon}" alt={name} />
            </a>
          </li>
        {/each}
      </ul>
    </nav>
  </header>

  <div class="main-content">
    <aside class="profile-topbar">
      <div class="avatar-frame">
        <img src="tu-foto.jpg" alt="Profile" />
      </div>
      <h2 class="neon-text">@{profile.name.toLowerCase()}</h2>
      <p class="stats">he / him • {profile.knowledge[0]} + 17teen</p>
      <p>{profile.bio}</p>
    </aside>
    <section>
      <article class="pixel-card skills">
        <h3 class="title-bar">SKILLS LIST</h3>
        <ul>
          {#each profile.knowledge as skill}
            <li><strong>{skill.toLowerCase()}</strong></li>
          {/each}
        </ul>
      </article>

      <div class="visual-footer">
        <img src="" alt="pixel-art" />
        <img src="" alt="pixel-art" />
        <img src="" alt="pixel-art" />
        <img src="" alt="pixel-art" />
        <img src="" alt="pixel-art" />
        <img src="" alt="pixel-art" />
      </div>
    </section>
  </div>
</main>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');

  :root {
    --bg: #0b0b12;
    --panel: #0f1530;
    --accent: #6ee7ff;
    --accent-2: #ff8bd6;
    --muted: #9aa4c0;
    --glass: rgba(255, 255, 255, 0.05);
  }

  /* RESET Y FULL SCREEN */
  :global(body, html) {
    margin: 0;
    padding: 0;
    height: 100vh;
    background-color: var(--bg);
    color: var(--muted);
    font-family: 'Press Start 2P', monospace;
    overflow: hidden;
  }

  /* SCANLINES EFECTO */
  .shell::before {
    content: " ";
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.1) 50%);
    background-size: 100% 4px;
    z-index: 10;
    pointer-events: none;
  }

  /* CONTENEDOR PRINCIPAL EN GRIDS */
  .shell {
    display: grid;
    grid-template-rows: 60px 1fr; /* Barra superior y contenido */
    height: 100vh;
    width: 100vw;
  }

  /* HEADER / TOP BAR */
  .top-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
    background: linear-gradient(180deg, var(--panel), transparent);
    border-bottom: 1px solid var(--glass);
  }

  .url-bar {
    font-size: 8px;
    color: var(--accent);
  }

  .social-list {
    display: flex;
    list-style: none;
    gap: 15px;
  }

  .social-btn img {
    width: 24px;
    filter: drop-shadow(0 0 5px var(--accent-2));
    transition: transform 0.2s;
  }

  .social-btn:hover img {
    transform: scale(1.2);
  }

  /* CUADRICULA DE CONTENIDO (ARRIBA Y ABAJO) */
  .main-content {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 40% 60%; /* Mantiene tu proporción original en móvil */
    padding: 20px;
    gap: 20px;
    overflow: hidden;
  }

  @media (min-width: 768px) {
    .main-content {
      grid-template-columns: 350px 1fr; /* Panel lateral fijo y resto flexible */
      grid-template-rows: 1fr; /* Altura completa */
    }
  }

  /* SECCIÓN PERFIL */
  .profile-topbar {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    background: var(--glass);
    border-radius: 10px;
    border: 1px solid rgba(255,255,255,0.05);
    padding: 20px;
    overflow-y: auto; /* Asegura scroll si el contenido es muy alto */
  }

  .avatar-frame img {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    border: 2px solid var(--accent);
    margin-bottom: 10px;
  }

  .neon-text {
    color: var(--accent);
    text-shadow: 0 0 10px var(--accent);
    font-size: 14px;
    margin: 5px 0;
  }

  .stats {
    font-size: 7px;
    color: var(--accent-2);
  }

  /* SECCIÓN ABAJO: SKILLS */
  section {
    display: grid;
    grid-template-rows: 1fr auto; /* Tarjeta de skills y visual footer */
    gap: 15px;
    overflow: hidden;
  }

  .pixel-card.skills {
    background: var(--panel);
    border: 2px solid var(--accent-2);
    border-radius: 5px;
    padding: 20px;
    overflow-y: auto;
    position: relative;
  }

  .title-bar {
    font-size: 10px;
    color: var(--bg);
    background: var(--accent-2);
    display: inline-block;
    padding: 5px 10px;
    margin-bottom: 15px;
  }

  ul {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 15px;
    list-style: none;
    padding: 0;
  }

  li {
    font-size: 8px;
    line-height: 1.5;
    padding: 8px;
    background: rgba(0,0,0,0.3);
    border-left: 3px solid var(--accent);
  }

  /* VISUAL FOOTER ICONOS */
  .visual-footer {
    display: flex;
    justify-content: center;
    gap: 10px;
    padding: 10px;
  }

  .visual-footer img {
    width: 30px;
    height: 30px;
    background: var(--glass);
    border-radius: 4px;
  }

  /* Scrollbar personalizado para que no rompa el estilo */
  ::-webkit-scrollbar {
    width: 5px;
  }
  ::-webkit-scrollbar-track {
    background: var(--bg);
  }
  ::-webkit-scrollbar-thumb {
    background: var(--accent-2);
  }
</style>