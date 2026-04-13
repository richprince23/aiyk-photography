<script setup lang="ts">
import { ref } from 'vue'

const faqs = [
  {
    q: 'What equipment do you use?',
    a: 'We shoot with professional-grade full-frame cameras and a curated selection of prime lenses. All sessions are delivered in high resolution with professional color grading.',
  },
  {
    q: 'How long does delivery take?',
    a: 'You will receive your edited gallery within 7 business days of the shoot. Rush delivery within 48 hours is available for an additional fee.',
  },
  {
    q: 'Do you travel for shoots?',
    a: 'Yes. We are available for travel across Ohio and beyond. Travel fees apply for locations more than 30 miles from Oxford, OH.',
  },
  {
    q: 'How is pricing structured?',
    a: 'Pricing is based on session type, duration, and usage rights. We offer transparent packages with no hidden fees. Contact us for a custom quote tailored to your project.',
  },
  {
    q: 'Will I receive the RAW files?',
    a: 'Yes. All packages include fully edited JPEGs and the original RAW files, giving you complete flexibility for future post-processing.',
  },
  {
    q: 'Do you provide styling or art direction?',
    a: 'We offer light art direction for brand sessions and can recommend local stylists. For larger campaigns requiring full styling teams, we are happy to coordinate with your existing creatives.',
  },
]

const faqSchema = {
  '@context': 'https://schema.org',
  '@type': 'FAQPage',
  mainEntity: faqs.map((faq) => ({
    '@type': 'Question',
    name: faq.q,
    acceptedAnswer: {
      '@type': 'Answer',
      text: faq.a,
    },
  })),
}

const openIndex = ref<number | null>(null)

function toggle(i: number) {
  openIndex.value = openIndex.value === i ? null : i
}
</script>

<template>
  <script type="application/ld+json" v-text="JSON.stringify(faqSchema)"></script>
  <section id="faq" class="faq-section">
    <div class="container">
      <div class="faq-layout">
        <!-- Label -->
        <div class="faq-label-col">
          <p class="section-label">FAQ</p>
          <h2 class="faq-title">
            Common<br /><em>Questions</em>
          </h2>
        </div>

        <!-- Accordion -->
        <div class="faq-accordion-col">
          <div class="accordion-list">
            <div
              v-for="(faq, i) in faqs"
              :key="faq.q"
              class="accordion-item"
            >
              <button
                class="accordion-trigger"
                @click="toggle(i)"
              >
                <span class="accordion-question" :class="openIndex === i ? 'question-open' : ''">
                  {{ faq.q }}
                </span>
                <span
                  class="accordion-icon"
                  :class="openIndex === i ? 'icon-open' : ''"
                >
                  <svg width="11" height="11" viewBox="0 0 12 12" fill="none">
                    <line x1="6" y1="0" x2="6" y2="12" stroke="currentColor" stroke-width="1.2"/>
                    <line x1="0" y1="6" x2="12" y2="6" stroke="currentColor" stroke-width="1.2"/>
                  </svg>
                </span>
              </button>
              <div v-if="openIndex === i" class="accordion-answer">
                <p>{{ faq.a }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.faq-section {
  background: var(--bg);
  padding: 8rem 0;
  border-top: 1px solid var(--divider);
}

.faq-layout {
  display: grid;
  grid-template-columns: 1fr;
  gap: 4rem;
}

@media (min-width: 1024px) {
  .faq-layout {
    grid-template-columns: 4fr 8fr;
    gap: 6rem;
    align-items: start;
  }

  .faq-label-col {
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

.faq-title {
  font-family: 'Playfair', Georgia, serif;
  font-size: clamp(2.2rem, 4vw, 3.25rem);
  color: var(--text);
  line-height: 1.2;
}

.faq-title em {
  font-style: italic;
  color: var(--text-muted);
}

.accordion-list {
  border-top: 1px solid var(--divider);
}

.accordion-item {
  border-bottom: 1px solid var(--divider);
}

.accordion-trigger {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.75rem 0;
  text-align: left;
  gap: 2rem;
  cursor: pointer;
  background: none;
  border: none;
}

.accordion-question {
  font-family: 'Playfair', Georgia, serif;
  font-size: 0.95rem;
  color: var(--text-muted);
  line-height: 1.5;
  transition: color 0.2s;
}

.question-open {
  color: var(--text);
}

.accordion-icon {
  color: var(--text-muted);
  flex-shrink: 0;
  width: 20px;
  height: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.25s, color 0.2s;
}

.icon-open {
  transform: rotate(45deg);
  color: var(--bronze);
}

.accordion-answer {
  padding-bottom: 1.75rem;
  padding-right: 3rem;
}

.accordion-answer p {
  color: var(--text-muted);
  font-size: 0.875rem;
  line-height: 1.8;
}
</style>
