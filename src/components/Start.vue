<script setup lang="ts"></script>

<template>
  <section id="home" class="hero">
    <div class="hero-innen">
      <p class="hero-kicker">SOFTWARETECHNIK-STUDENT · 3. SEMESTER</p>

      <h1 class="hero-title">
        Ich baue <span>Software-Projekte</span><br />
        während ich lerne.
      </h1>

      <p class="hero-subtitle">
        Fokus auf moderne Web-Apps mit Vue & TypeScript, erste
        Backend-Erfahrungen und viel Neugier für sauberen Code und gute
        Architektur.
      </p>

      <ul class="hero-points">
        <li>🚀 Eigene Projekte statt nur Theorie</li>
        <li>🧠 Interesse an Clean Code & Architektur</li>
        <li>🌐 Web, Datenbanken & ein bisschen DevOps</li>
      </ul>

      <div class="hero-actions">
        <a href="#projekte" class="btn-primary">Projekte anschauen</a>
        <a href="#lebenslauf" class="btn-secondary">Lebenslauf öffnen</a>
      </div>

      <p class="hero-loop">lernen · coden · verbessern · repeat</p>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: calc(100vh - 120px); /* Platz für deine Navbar */
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0 2rem;
}

.hero-innen {
  text-align: center;
  max-width: 900px;
  margin: 0 auto;
}

/* Kicker oben */
.hero-kicker {
  font-size: 14px;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  opacity: 0.75;
  margin-bottom: 16px;
}

/* Headline */
.hero-title {
  font-size: clamp(40px, 6vw, 62px);
  line-height: 1.15;
  font-weight: 600;
  margin: 0 0 28px;
}

.hero-title span {
  color: var(--detail);
}

/* Untertitel */
.hero-subtitle {
  font-size: 17px;
  max-width: 640px;
  margin: 0 auto 26px;
  opacity: 0.85;
  line-height: 1.6;
}

/* Punkte-Liste */
.hero-points {
  list-style: none;
  padding: 0;
  margin: 0 auto 32px;

  display: flex;
  flex-wrap: wrap;
  gap: 14px 26px;
  justify-content: center;

  font-size: 15px;
  opacity: 0.9;
}

/* Button-Bereich */
.hero-actions {
  display: flex;
  justify-content: center;
  gap: 22px;
  margin-bottom: 26px;
}

/* Buttons */
.btn-primary,
.btn-secondary {
  display: inline-block;
  padding: 12px 28px;
  font-size: 16px;
  font-family: var(--font);
  border-radius: 12px;
  text-decoration: none;
  transition: 0.15s ease;
}

.btn-primary {
  background: var(--detail);
  color: #0b0b12;
  box-shadow: 0 18px 35px rgba(0, 0, 0, 0.55);
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 22px 40px rgba(0, 0, 0, 0.65);
}

.btn-secondary {
  border: 1px solid rgba(148, 163, 184, 0.6);
  background: rgba(17, 17, 27, 0.8);
  color: var(--text-color);
}

.btn-secondary:hover {
  border-color: var(--detail);
  transform: translateY(-2px);
}

/* Unterer Loop-Satz */
.hero-loop {
  font-size: 14px;
  letter-spacing: 0.22em;
  opacity: 0.75;
  margin-top: 10px;
}

/* Mobile */
@media (max-width: 640px) {
  .hero {
    padding: 0 1.5rem;
  }

  .hero-actions {
    flex-direction: column;
  }

  .btn-primary,
  .btn-secondary {
    width: 100%;
    text-align: center;
  }
}
</style>
