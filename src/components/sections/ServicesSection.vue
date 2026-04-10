<script setup lang="ts">
const services = [
  {
    number: '01',
    title: 'Fashion & Editorial',
    description:
      'Striking imagery for brands and publications, capturing style, personality, and the essence of your creative vision.',
    image: '/images/DA6gpmF5zC0WZ5S1zLWCKOCU.jpeg',
    alt: 'Fashion and editorial photography',
    tags: ['Lookbooks', 'Campaigns', 'Editorial'],
  },
  {
    number: '02',
    title: 'Brand & Commercial',
    description:
      'High-impact photography for businesses, campaigns, and products that drives conversions and elevates your brand identity.',
    image: '/images/gJutA4fKgkN4S7Q93bbnfDZwDdo.jpeg',
    alt: 'Brand and commercial photography',
    tags: ['Product', 'Advertising', 'E-commerce'],
  },
  {
    number: '03',
    title: 'Portrait & Studio',
    description:
      'Professional headshots and portraits tailored to reflect your personality and brand — in studio or on location.',
    image: '/images/MbsRlJjTMsitSvfqgiHjAnlMPk.png',
    alt: 'Portrait and studio photography',
    tags: ['Headshots', 'Studio', 'On-location'],
  },
]
</script>

<template>
  <section id="services" class="services-section">
    <div class="container">
      <!-- Section header -->
      <div class="services-header">
        <div>
          <p class="section-label">What We Offer</p>
          <h2 class="section-title">Services</h2>
        </div>
        <a href="#contact" class="header-link hidden md:inline-block">
          Request a quote
        </a>
      </div>

      <!-- Service rows -->
      <div class="services-list">
        <div
          v-for="service in services"
          :key="service.title"
          class="service-row group"
        >
          <!-- Number -->
          <div class="service-number">
            <span>{{ service.number }}</span>
          </div>

          <!-- Image -->
          <div class="service-image">
            <img
              :src="service.image"
              :alt="service.alt"
              class="service-img"
            />
          </div>

          <!-- Content -->
          <div class="service-content">
            <h3 class="service-title">{{ service.title }}</h3>
            <p class="service-desc">{{ service.description }}</p>
            <div class="service-tags">
              <span
                v-for="tag in service.tags"
                :key="tag"
                class="service-tag"
              >
                {{ tag }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.services-section {
  background: var(--bg);
  padding: 8rem 0 5rem;
}

.services-header {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  margin-bottom: 5rem;
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

.header-link {
  font-size: 0.62rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--text-muted);
  border-bottom: 1px solid var(--divider);
  padding-bottom: 0.2rem;
  transition: all 0.2s;
}

.header-link:hover {
  color: var(--bronze);
  border-bottom-color: var(--bronze);
}

.services-list {
  display: flex;
  flex-direction: column;
}

.service-row {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  padding: 4rem 0;
  border-bottom: 1px solid var(--divider);
  cursor: default;
}

@media (min-width: 1024px) {
  .service-row {
    grid-template-columns: 3rem 2fr 3fr;
    gap: 4rem;
    align-items: center;
  }
}

.service-number {
  display: flex;
  align-items: center;
}

.service-number span {
  font-size: 0.6rem;
  letter-spacing: 0.2em;
  color: var(--text-muted);
  opacity: 0.5;
}

.service-image {
  aspect-ratio: 4 / 3;
  overflow: hidden;
  background: var(--bg-alt);
}

.service-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: saturate(0.8);
  transition: transform 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94), filter 0.5s;
}

.group:hover .service-img {
  transform: scale(1.04);
  filter: saturate(1);
}

.service-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.service-title {
  font-family: 'Playfair', Georgia, serif;
  font-size: clamp(1.6rem, 3vw, 2.5rem);
  color: var(--text);
  margin-bottom: 1.25rem;
  line-height: 1.15;
  transition: color 0.2s;
}

.group:hover .service-title {
  color: var(--ink);
}

.service-desc {
  color: var(--text-muted);
  line-height: 1.75;
  margin-bottom: 2rem;
  max-width: 28rem;
  font-size: 0.9rem;
}

.service-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.service-tag {
  font-size: 0.58rem;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--text-muted);
  border: 1px solid var(--divider-mid);
  padding: 0.35rem 0.9rem;
  transition: all 0.2s;
}

.group:hover .service-tag {
  border-color: rgba(201, 169, 110, 0.25);
  color: var(--bronze);
}
</style>
