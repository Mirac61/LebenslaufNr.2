<script setup lang="ts">
// Später kannst du hier z. B. Scroll-Logik, Aktive Section, Darkmode usw. reinpacken.
</script>

<template>
  <nav class="navbar">
    <div class="navbar-innen">
      <div class="navbar-name">
        <li><a>Mirac Sancak</a></li>
      </div>

      <ul class="navbar-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#projekte">Projekte</a></li>
        <li><a href="#faehigkeiten">Fähigkeiten</a></li>
        <li><a href="#werdegang">Werdegang</a></li>
        <li><a href="#kontakt">Kontakt</a></li>
        <li><a href="#lebenslauf">Lebenslauf</a></li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  position: fixed;
  max-width: 98%;
  width: 96%;

  top: 10px;
  height: 70px;
  left: 0;
  right: 0;

  margin: 0 auto;
  justify-content: center;
  background: var(--glas-bg);
  display: flex;
  align-items: center;
  border-radius: 25px;
}

.navbar-innen {
  width: 100%;
  padding: 0 24px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navbar-links {
  list-style: none;
  display: flex;
  gap: 32px;
  padding: 0;
  margin: 0 auto;
  text-align: ce;
}

.navbar-links a {
  display: inline-block; /* wichtig für transform */
  color: var(--text-color);
  font-size: 16px;
  text-decoration: none;
  font-family: var(--font);
  border: none;
  background: none !important;
  box-shadow: none !important;
  padding: 0 !important;
  transition:
    color 0.2s ease,
    transform 0.2s ease; /* transform mit-animieren */
}

.navbar-links a:hover {
  color: var(--detail);
  transform: translateY(-1px);
}

.navbar-links a.active {
  color: var(--detail);
}

@media (max-width: 800px) {
  .navbar-links {
    gap: 18px;
  }
}

@media (max-width: 600px) {
  .navbar-links {
    display: none;
  }
}
</style>
