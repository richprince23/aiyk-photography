<script setup lang="ts">
const projects = [
  {
    image: '/images/3WwYqzhCzeuAA0tSlhUw9w1oc.jpeg',
    category: 'Fashion & Editorial',
    title: 'Golden Hour',
    year: '2024',
    size: 'large',
  },
  {
    image: '/images/wHtIRUAFLgs4Y2UvqCL8BDqX9cQ.jpeg',
    category: 'Portrait & Studio',
    title: 'Coastal Warmth',
    year: '2024',
    size: 'small',
  },
  {
    image: '/images/6gw1k929tTnlbEBhukcXvrqToJo.jpeg',
    category: 'Brand & Commercial',
    title: 'Easy Living',
    year: '2023',
    size: 'small',
  },
  {
    image: '/images/K13ohMB77Ii9gPrk1P4Jg7MYVo.png',
    category: 'Fashion & Editorial',
    title: 'Sun Veil',
    year: '2023',
    size: 'medium',
  },
  {
    image: '/images/pMd4SDTzuamCixIwDM3a5RZA2Oo.jpeg',
    category: 'Brand & Commercial',
    title: 'Refined Detail',
    year: '2024',
    size: 'medium',
  },
]
</script>

<template>
  <section id="portfolio" class="portfolio-section">
    <div class="container">
      <!-- Header -->
      <div class="portfolio-header">
        <div>
          <p class="section-label">Selected Work</p>
          <h2 class="section-title">Portfolio</h2>
        </div>
        <a href="#contact" class="header-link hidden md:inline-block">
          View all projects &rarr;
        </a>
      </div>

      <!-- Editorial grid -->
      <div class="portfolio-grid">
        <!-- Large feature -->
        <div class="grid-item grid-large group">
          <div class="item-image">
            <img :src="projects[0].image" :alt="projects[0].title" class="item-img" />
            <div class="item-hover-overlay">
              <span class="view-label">View Project</span>
            </div>
          </div>
          <div class="item-meta">
            <div>
              <p class="item-category">{{ projects[0].category }}</p>
              <p class="item-title">{{ projects[0].title }}</p>
            </div>
            <span class="item-year">{{ projects[0].year }}</span>
          </div>
        </div>

        <!-- Right column stacked -->
        <div class="grid-right-col">
          <div
            v-for="project in projects.slice(1, 3)"
            :key="project.title"
            class="grid-item group"
          >
            <div class="item-image item-image--short">
              <img :src="project.image" :alt="project.title" class="item-img" />
              <div class="item-hover-overlay">
                <span class="view-label">View Project</span>
              </div>
            </div>
            <div class="item-meta">
              <div>
                <p class="item-category">{{ project.category }}</p>
                <p class="item-title">{{ project.title }}</p>
              </div>
              <span class="item-year">{{ project.year }}</span>
            </div>
          </div>
        </div>

        <!-- Bottom two equal -->
        <div class="grid-item group grid-bottom-left">
          <div class="item-image item-image--wide">
            <img :src="projects[3].image" :alt="projects[3].title" class="item-img" />
            <div class="item-hover-overlay">
              <span class="view-label">View Project</span>
            </div>
          </div>
          <div class="item-meta">
            <div>
              <p class="item-category">{{ projects[3].category }}</p>
              <p class="item-title">{{ projects[3].title }}</p>
            </div>
            <span class="item-year">{{ projects[3].year }}</span>
          </div>
        </div>

        <div class="grid-item group grid-bottom-right">
          <div class="item-image item-image--wide">
            <img :src="projects[4].image" :alt="projects[4].title" class="item-img" />
            <div class="item-hover-overlay">
              <span class="view-label">View Project</span>
            </div>
          </div>
          <div class="item-meta">
            <div>
              <p class="item-category">{{ projects[4].category }}</p>
              <p class="item-title">{{ projects[4].title }}</p>
            </div>
            <span class="item-year">{{ projects[4].year }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.portfolio-section {
  background: var(--bg);
  padding: 8rem 0;
}

.portfolio-header {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  margin-bottom: 4rem;
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
  transition: color 0.2s;
}

.header-link:hover {
  color: var(--bronze);
}

.portfolio-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 0.75rem;
}

@media (min-width: 768px) {
  .portfolio-grid {
    grid-template-columns: 7fr 5fr;
    grid-template-rows: auto auto;
  }

  .grid-large {
    grid-column: 1;
    grid-row: 1;
  }

  .grid-right-col {
    grid-column: 2;
    grid-row: 1;
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  .grid-bottom-left {
    grid-column: 1;
    grid-row: 2;
  }

  .grid-bottom-right {
    grid-column: 2;
    grid-row: 2;
  }
}

.grid-item {
  cursor: pointer;
  display: flex;
  flex-direction: column;
}

.item-image {
  position: relative;
  overflow: hidden;
  background: var(--bg-alt);
  min-height: 320px;
}

@media (min-width: 768px) {
  .grid-large .item-image {
    min-height: 520px;
  }

  .item-image--short {
    min-height: 240px;
  }

  .item-image--wide {
    min-height: 300px;
  }
}

.item-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  position: absolute;
  inset: 0;
  filter: saturate(0.75);
  transition: transform 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94), filter 0.5s;
}

.group:hover .item-img {
  transform: scale(1.05);
  filter: saturate(1);
}

.item-hover-overlay {
  position: absolute;
  inset: 0;
  background: rgba(250, 248, 245, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.35s;
}

.group:hover .item-hover-overlay {
  opacity: 1;
}

.view-label {
  font-size: 0.6rem;
  letter-spacing: 0.25em;
  text-transform: uppercase;
  color: var(--text);
  border: 1px solid rgba(26, 25, 23, 0.4);
  padding: 0.6rem 1.25rem;
}

.item-meta {
  display: flex;
  align-items: baseline;
  justify-content: space-between;
  padding-top: 1rem;
  padding-bottom: 0.5rem;
}

.item-category {
  font-size: 0.6rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--bronze);
  margin-bottom: 0.3rem;
  opacity: 0.7;
}

.item-title {
  font-family: 'Playfair', Georgia, serif;
  font-size: 1.05rem;
  color: var(--text);
  transition: color 0.2s;
}

.group:hover .item-title {
  color: var(--ink);
}

.item-year {
  font-size: 0.6rem;
  color: var(--text-muted);
  opacity: 0.5;
  letter-spacing: 0.05em;
}
</style>
