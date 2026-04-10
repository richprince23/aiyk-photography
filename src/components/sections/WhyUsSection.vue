<script setup lang="ts">
const stats = [
  { value: '50+', label: 'Brands Served' },
  { value: '7', label: 'Day Turnaround' },
  { value: '100%', label: 'Client Satisfaction' },
  { value: 'Full', label: 'Licensing Included' },
]
</script>

<template>
  <section id="about" class="why-section">
    <div class="container">
      <div class="why-grid">
        <!-- Left -->
        <div class="why-left">
          <p class="section-label">Why Work With Us</p>
          <h2 class="why-headline">
            Consistency and quality —<br /><em>every time.</em>
          </h2>
          <p class="why-body">
            We combine a collaborative approach with strategic thinking to deliver imagery that doesn't just look good — it works hard for your brand across every channel and campaign.
          </p>
          <a href="#contact" class="why-cta">
            Start a project
          </a>
        </div>

        <!-- Right: stats -->
        <div class="stats-grid">
          <div
            v-for="stat in stats"
            :key="stat.label"
            class="stat-cell"
          >
            <p class="stat-value">{{ stat.value }}</p>
            <p class="stat-label">{{ stat.label }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.why-section {
  background: var(--bg-alt);
  padding: 8rem 0;
  border-top: 1px solid var(--divider);
}

.why-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 5rem;
  align-items: start;
}

@media (min-width: 1024px) {
  .why-grid {
    grid-template-columns: 1fr 1fr;
    gap: 6rem;
  }

  .why-left {
    position: sticky;
    top: 8rem;
  }
}

.section-label {
  font-size: 0.62rem;
  letter-spacing: 0.28em;
  text-transform: uppercase;
  color: var(--bronze);
  margin-bottom: 1.25rem;
}

.why-headline {
  font-family: 'Playfair', Georgia, serif;
  font-size: clamp(2.2rem, 4vw, 3.25rem);
  color: var(--text);
  line-height: 1.2;
  margin-bottom: 2rem;
  letter-spacing: -0.01em;
}

.why-headline em {
  font-style: italic;
  color: var(--text-muted);
}

.why-body {
  color: var(--text-muted);
  line-height: 1.8;
  font-size: 0.9rem;
  max-width: 26rem;
  margin-bottom: 2.5rem;
}

.why-cta {
  display: inline-block;
  font-size: 0.65rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  border: 1px solid rgba(201, 169, 110, 0.4);
  color: var(--bronze);
  padding: 0.9rem 2rem;
  transition: all 0.25s;
}

.why-cta:hover {
  background: var(--bronze);
  color: #fff;
  border-color: var(--bronze);
}

.stats-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1px;
  background: var(--divider-mid);
}

.stat-cell {
  background: var(--bg);
  padding: 2.75rem 2.5rem;
  transition: background 0.25s;
}

.stat-cell:hover {
  background: var(--bg-alt);
}

.stat-value {
  font-family: 'Playfair', Georgia, serif;
  font-size: clamp(2.5rem, 5vw, 4rem);
  color: var(--text);
  margin-bottom: 0.6rem;
  line-height: 1;
}

.stat-label {
  font-size: 0.6rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  color: var(--bronze);
  opacity: 0.65;
}
</style>
