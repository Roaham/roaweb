<script>
  import "../app.css";
</script>

<div class="ps1-shell">
  <nav class="ps1-nav">
    <a href="/" class="logo">ROA</a>

    <div class="links">
      <a href="/" class="nav-link">Home</a>
      <a href="/projects" class="nav-link">Projects</a>
      <a href="/about" class="nav-link">About Me</a>
    </div>
  </nav>


  <main class="content">
    <slot />
  </main>

  <footer class="ps1-footer">Roaham's Web · Made by Roaham</footer>
</div>
