<script setup lang="ts">
import { ref, onMounted, onUnmounted } from "vue";

// Lebenslauf-Bilder
import lebenslaufHell from "@/assets/Lebenslauf/LebenslaufHell.png";
import lebenslaufDunkel from "@/assets/Lebenslauf/LebenslaufDunkel.png";

// Zeiterfassung-Bilder (liegen unter src/assets/Lebenslauf/Zeit)
import zeit1 from "@/assets/Zeit/ZeiterfassungEins.png";
import zeit2 from "@/assets/Zeit/ZeiterfassungZwei.png";
import zeit3 from "@/assets/Zeit/ZeiterfassungDrei.png";
import zeit4 from "@/assets/Zeit/ZeiterfassungVier.png";

const lebenslaufBilder = [lebenslaufHell, lebenslaufDunkel];
const zeiterfassungBilder = [zeit1, zeit2, zeit3, zeit4];

const lebenslaufIndex = ref(0);
const zeitIndex = ref(0);

let timer: number | null = null;

onMounted(() => {
  timer = window.setInterval(() => {
    lebenslaufIndex.value =
      (lebenslaufIndex.value + 1) % lebenslaufBilder.length;

    zeitIndex.value = (zeitIndex.value + 1) % zeiterfassungBilder.length;
  }, 5000);
});

onUnmounted(() => {
  if (timer !== null) clearInterval(timer);
});
</script>

<template>
  <section id="projekte" class="projekte">
    <div class="sektion-innen">
      <h2 class="sektion-titel">Projekte</h2>

      <div class="box-grid">
        <!-- Linke Box: Interaktiver Lebenslauf -->
        <div class="box">
          <h3>Interaktiver Lebenslauf</h3>

          <div class="vorschau-wrapper">
            <Transition name="slide">
              <img
                :key="lebenslaufIndex"
                :src="lebenslaufBilder[lebenslaufIndex]"
                alt="Lebenslauf Vorschau"
                class="vorschau"
              />
            </Transition>
          </div>

          <p>
            Ein moderner, interaktiver Lebenslauf mit Fokus auf ein sauberes
            Developer(Apple)-Design mit klarer Struktur.
          </p>

          <div class="projekt-footer">
            <span class="tech-btn">HTML · CSS · JavaScript</span>

            <a
              href="https://github.com/Mirac61/Lebenslauf_IT/tree/main"
              target="_blank"
              class="github-btn"
            >
              <img src="@/assets/githubmark.png" alt="GitHub" />
            </a>
          </div>
        </div>

        <!-- Rechte Box: Zeiterfassungssoftware -->
        <div class="box">
          <h3>Zeiterfassungssystem</h3>

          <div class="vorschau-wrapper">
            <Transition name="slide">
              <img
                :key="zeitIndex"
                :src="zeiterfassungBilder[zeitIndex]"
                alt="Zeiterfassung Vorschau"
                class="vorschau"
              />
            </Transition>
          </div>

          <p>
            Eine moderne, webbasierte Zeiterfassungssoftware mit Rollen,
            Arbeitszeitverwaltung und übersichtlichem Dashboard.
          </p>

          <div class="projekt-footer">
            <span class="tech-btn">C# · ASP.NET Core · SQLite</span>

            <a
              href="https://github.com/DanielTrbara/Zeiterfassung"
              target="_blank"
              class="github-btn"
            >
              <img src="@/assets/githubmark.png" alt="GitHub" />
            </a>
          </div>
        </div>

        <!-- Restliche Boxen wie gehabt -->
        <div class="box">
          <h3>Rechnung Ersteller-Tool</h3>
          <p>Tool zum Erstellen und Verwalten von Rechnungen.</p>
          <span class="meta">C# · ASP.NET</span>
        </div>

        <div class="box">
          <h3>Coming Soon</h3>
          <p>Neues Projekt wird bald ergänzt.</p>
          <span class="meta">—</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.projekte {
  padding: 80px 2rem;
}

.sektion-titel {
  font-size: 28px;
  margin-bottom: 20px;
}

.box-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
}

.box {
  background: rgba(17, 17, 27, 0.85);
  border-radius: 16px;
  padding: 20px;
  border: 1px solid rgba(148, 163, 184, 0.3);
}

.box h3 {
  margin: 0 0 8px;
}

.box p {
  margin: 0 0 10px;
  font-size: 14px;
}

.meta {
  opacity: 0.7;
  font-size: 13px;
}

.vorschau-wrapper {
  position: relative;
  overflow: hidden;
  border-radius: 12px;
  margin-bottom: 12px;
  aspect-ratio: 16 / 9;
}

.vorschau {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Footer-Buttons */
.projekt-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 12px;
}

.tech-btn,
.github-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;

  padding: 6px 12px;
  border-radius: 10px;

  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.12);
  backdrop-filter: blur(10px);

  font-size: 13px;
  color: #e2e8f0;
  text-decoration: none;
  cursor: pointer;

  transition:
    transform 0.2s ease,
    opacity 0.2s ease;
}

.tech-btn:hover,
.github-btn:hover {
  transform: translateY(-2px);
}

.github-btn img {
  width: 20px;
  height: 20px;
}
</style>
