<script>
  import { base } from '$app/paths';

  const profile = {
    name: "roaham",
    bio: "Hi! — I'm Roaham. I lov Programmimg nd Cybersecurity, yet another IT student.",
    email: "hyperoa@proton.me",
    knowledge: [
      "Python (Intermediate):\n Data analysis, automation, and Flask back-ends.",
      "Java (Intermediate):\n OOP, Spring Boot basics, and application logic.",
      "Svelte (Intermediate):\n Component-based UI and reactive state management.",   
      "CSS & HTML (Intermediate):\n Responsive design (Flex/Grid) and semantic structures.",
      "JavaScript (Beginner):\n Core syntax, DOM manipulation, and ES6+.",
      "SQL (Beginner):\n Basic queries, table design, and relational data.",
      "Linux (Intermediate): Proficiency in CLI, and Bash scripting for task automation."
    ]
  };

  const socialLinks = [
    { name: 'Discord', href: 'https://discord.gg/wtEhz63dYf', icon: '/discord.svg' },
    { name: 'X', href: 'https://x.com/GRorich10', icon: '/twitter.svg' },
    { name: 'Steam', href: 'https://steamcommunity.com/profiles/76561199106558504/', icon: '/steam.svg' },
    { name: 'Github', href: 'https://github.com/Roaham', icon: '/github.svg' }
  ];
</script>

<main class="shell">
  <div class="main-content">
    <aside class="profile-topbar">
      <div class="avatar-frame">
        <img src="/lain.jpg" alt="Profile" />
      </div>
      <h2 class="neon-text">@{profile.name}</h2>
      <p class="stats">he / him • {profile.email} • 17teen</p>
      <p>{profile.bio}</p>
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
    </aside>
    <section>
      <article class="pixel-card skills">
        <h3 class="title-bar">SKILLS LIST</h3>
        <ul class="skills-list">
          {#each profile.knowledge as skill}
            <li><strong>{skill}</strong></li>
          {/each}
        </ul>
      </article>
    </section>
  </div>
</main>

<style>
  /* MAIN */
  .shell {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    width: 100%;
  }

  .main-content {
    display: grid;
    grid-template-columns: 1fr;
    padding: 20px;
    gap: 20px;
    flex: 1;
  }

  @media (min-width: 768px) {
    .main-content {
      grid-template-columns: 350px 1fr;
    }
  }

  /* PROFILE */
  .profile-topbar {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start; 
    text-align: center;
    background: var(--panel);
    border-radius: 10px;
    border: 2px solid var(--accent-2);
    padding: 30px 20px;
    height: fit-content;
  }

  .avatar-frame img {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    border: 2px solid var(--accent);
    margin-bottom: 15px;
    object-fit: cover;
  }

  .neon-text {
    color: var(--accent);
    text-shadow: 0 0 10px var(--accent);
    font-size: 14px;
    margin: 10px 0;
  }

  .stats {
    font-size: 8px;
    color: var(--accent-2);
    margin-bottom: 15px;
  }

  .social-list {
    display: flex;
    list-style: none;
    gap: 30px;
    padding: 0;
  }

  .social-btn img {
    width: 35px;
    transition: transform 0.4s;
    filter: drop-shadow(0 0 8px var(--accent-2));
  }

  .social-btn img:hover {
    transform: scale(1.5);
  }

  /* SKILLS */
  section {
    display: flex;
    flex-direction: column;
    gap: 15px;
  }

  .pixel-card.skills {
    background: var(--panel);
    border: 2px solid var(--accent-2);
    border-radius: 5px;
    padding: 20px;
  }

  .title-bar {
    font-size: 10px;
    color: var(--bg);
    background: var(--accent-2);
    display: inline-block;
    padding: 5px 10px;
    margin-bottom: 20px;
  }

  .skills-list {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 10px;
    list-style: none;
    padding: 0;
  }

  .skills-list li {
    font-size: 9px;
    line-height: 1.4;
    padding: 10px;
    background: rgba(0,0,0,0.4);
    border-left: 3px solid var(--accent);
  }
</style>