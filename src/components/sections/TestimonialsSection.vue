<script setup lang="ts">
import { onMounted, onUnmounted } from 'vue'

const testimonials = [
  {
    quote:
      'aiky completely transformed our product line visuals. The attention to detail and ability to capture our brand identity was remarkable. Our conversion rate increased by 30% after the rebrand.',
    name: 'Marcus Webb',
    role: 'Creative Director',
    company: 'Forma Studio',
    rating: 5,
  },
  {
    quote:
      'Working with aiky was effortless. They understood exactly what we needed for our editorial campaign without us having to over-explain. The results were beyond what we imagined.',
    name: 'Jenna Alcott',
    role: 'Founder',
    company: 'Alcott Apparel',
    rating: 5,
  },
  {
    quote:
      'The 7-day turnaround is real. We had campaign-ready imagery before our deadline, and the quality was immaculate. We will not go anywhere else for our photography needs.',
    name: 'Daniel Osei',
    role: 'Marketing Lead',
    company: 'Northfield Brands',
    rating: 5,
  },
]

const reviewSchema = {
  '@context': 'https://schema.org',
  '@type': 'LocalBusiness',
  name: 'aiky Photography',
  review: testimonials.map((t) => ({
    '@type': 'Review',
    reviewRating: {
      '@type': 'Rating',
      ratingValue: t.rating,
      bestRating: 5,
    },
    author: {
      '@type': 'Person',
      name: t.name,
    },
    reviewBody: t.quote,
  })),
  aggregateRating: {
    '@type': 'AggregateRating',
    ratingValue: 5,
    reviewCount: testimonials.length,
    bestRating: 5,
  },
}

let schemaTag: HTMLScriptElement | null = null

onMounted(() => {
  schemaTag = document.createElement('script')
  schemaTag.type = 'application/ld+json'
  schemaTag.textContent = JSON.stringify(reviewSchema)
  document.head.appendChild(schemaTag)
})

onUnmounted(() => {
  schemaTag?.remove()
})
</script>

<template>
  <section id="testimonials" class="testimonials-section">
    <div class="container">
      <!-- Header -->
      <div class="testimonials-header">
        <div>
          <p class="section-label">Client Feedback</p>
          <h2 class="section-title">What Clients Say</h2>
        </div>
      </div>

      <!-- Testimonials -->
      <div class="testimonials-grid">
        <div
          v-for="t in testimonials"
          :key="t.name"
          class="testimonial-card"
        >
          <div class="testimonial-mark">&ldquo;</div>
          <p class="testimonial-quote">{{ t.quote }}</p>
          <div class="testimonial-author">
            <p class="author-name">{{ t.name }}</p>
            <p class="author-role">{{ t.role }}, {{ t.company }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.testimonials-section {
  background: var(--bg-alt);
  padding: 8rem 0;
  border-top: 1px solid var(--divider);
}

.testimonials-header {
  margin-bottom: 4rem;
  padding-bottom: 2rem;
  border-bottom: 1px solid var(--divider);
}

.section-label {
  font-size: 0.62rem;
  letter-spacing: 0.28em;
  text-transform: uppercase;
  color: var(--bronze);
  margin-bottom: 0.75rem;
}

.section-title {
  font-family: 'Playfair', Georgia, serif;
  font-size: clamp(2.2rem, 4vw, 3.5rem);
  color: var(--text);
  line-height: 1.1;
}

.testimonials-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2px;
  background: var(--divider-mid);
}

@media (min-width: 1024px) {
  .testimonials-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

.testimonial-card {
  background: var(--bg-alt);
  padding: 3rem 2.5rem;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  transition: background 0.25s;
}

.testimonial-card:hover {
  background: var(--bg);
}

.testimonial-mark {
  font-family: 'Playfair', Georgia, serif;
  font-size: 4rem;
  line-height: 1;
  color: var(--bronze);
  opacity: 0.3;
  margin-bottom: -0.5rem;
}

.testimonial-quote {
  font-family: 'Playfair', Georgia, serif;
  font-style: italic;
  color: var(--text-muted);
  line-height: 1.75;
  font-size: 0.95rem;
  flex: 1;
}

.testimonial-author {
  border-top: 1px solid var(--divider);
  padding-top: 1.5rem;
}

.author-name {
  font-size: 0.8rem;
  color: var(--text);
  font-weight: 500;
  margin-bottom: 0.3rem;
}

.author-role {
  font-size: 0.65rem;
  letter-spacing: 0.05em;
  color: var(--bronze);
  opacity: 0.6;
}
</style>
