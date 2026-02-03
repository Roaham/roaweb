<script>
  import { base } from '$app/paths';

  const profile = {
    name: "Roaham",
    bio: "Hola — soy Roaham. Me gusta la cyberseguridad, programar, la historia, leer y los videojueguitos",
    email: "hyperoa@proton.me",
    knowledge: ["Python", "Java", "CSS", "HTML", "JavaScript", "SQL", "Svelte"]
  };

  const socialLinks = [
    { name: 'Discord', href: 'https://discord.gg/wtEhz63dYf', icon: '/discord.svg' },
    { name: 'X', href: 'https://x.com/GRorich10', icon: '/twitter.svg' },
    { name: 'Steam', href: 'https://steamcommunity.com/...', icon: '/steam.svg' },
    { name: 'Github', href: 'https://github.com/Roaham', icon: '/github.svg' }
  ];
</script>

<section class="about">
  <h2 class="section-title">About Me</h2>

  <div class="about-grid">
    <div class="avatar">
      <img src="{base}/lain.jpg" alt="Roaham" />
    </div>
    
    <div class="bio">
      <p>{profile.bio}</p>

      <ul>
        <li><span class="label">Knowledge:</span> {profile.knowledge.join(', ')}</li>
        <li><span class="label">Contact via -></span> 
          <a href="mailto:{profile.email}" class="proj-link">{profile.email}</a>
        </li>
        
        <li class="social-wrapper">
          {#each socialLinks as { name, href, icon }}
            <a {href} target="_blank" rel="noopener noreferrer" title={name} class="social-btn">
              <img src="{base}{icon}" alt={name} />
            </a>
          {/each}
        </li>
      </ul>
    </div>
  </div>
</section>