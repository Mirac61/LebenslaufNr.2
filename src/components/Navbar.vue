<script setup lang="ts">
// Später kannst du hier z. B. Scroll-Logik, Aktive Section, Darkmode usw. reinpacken.
</script>

<template>
  <nav class="nav">
    <div class="nav-innen">
      <div class="nav-name">
        Mirac Sancak
      </div>

      <ul class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#bildung">Bildung</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#kontakt">Kontakt</a></li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
.nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 70px;
  background: var(--background);
  display: flex;
  align-items: center;
}

.nav-innen {
  width: 100%;
  padding: 0 24px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-name {
  font-size: 26px;
  font-weight: 700;
  color: var(--text-color);
  letter-spacing: 0.5px;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 32px;
  padding: 0;
  margin: 0;
}

.nav-links a {
  display: inline;
  color: var(--text-color);
  font-size: 16px;
  text-decoration: none;
  border: none;
  transition: color 0.2s ease;
  background: none !important;
  box-shadow: none !important;
  padding: 0 !important;
}

.nav-links a:hover {
  color: var(--detail);
}

.nav-links a.active {
  color: var(--detail);
}

@media (max-width: 800px) {
  .nav-links {
    gap: 18px;
  }
}

@media (max-width: 600px) {
  .nav-links {
    display: none;
  }
}

</style>