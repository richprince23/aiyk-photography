<template>
  <section id="home" class="hero">
    <!-- Full-bleed background image -->
    <div class="hero-bg">
      <img src="/images/pMd4SDTzuamCixIwDM3a5RZA2Oo.jpeg" alt="AIYK Photography" class="hero-img" />
      <div class="hero-overlay"></div>
    </div>

    <!-- Top-right location tag -->
    <div class="hero-location">
      <span class="location-dot"></span>
      Oxford, OH
    </div>

    <!-- Bottom editorial text block -->
    <div class="hero-content">
      <div class="container hero-inner">
        <div class="hero-eyebrow text-yellow-500">
          <span class="eyebrow-line"></span>
          Commercial Photography Services
        </div>
        <h1 class="hero-headline">
          Every photograph<br />
          <em>should make<br />an impact.</em>
        </h1>
        <div class="hero-actions">
          <a href="#contact" class="hero-btn-primary">Book a Session</a>
          <a href="#portfolio" class="hero-btn-secondary">
            View Work
            <span class="btn-arrow">&#x2192;</span>
          </a>
        </div>
      </div>
    </div>

    <!-- Scroll indicator -->
    <div class="scroll-indicator hidden lg:flex">
      <div class="scroll-line">
        <div class="scroll-fill"></div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  height: 100svh;
  min-height: 640px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
}

.hero-bg {
  position: absolute;
  inset: 0;
}

.hero-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: saturate(0.65);
}

.hero-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top,
      rgba(250, 248, 245, 0.92) 0%,
      rgba(250, 248, 245, 0.4) 45%,
      rgba(250, 248, 245, 0.05) 100%);
}

.hero-location {
  position: absolute;
  top: 96px;
  right: 2rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 0.62rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  color: rgba(26, 25, 23, 0.45);
  z-index: 1;
}

.location-dot {
  width: 4px;
  height: 4px;
  border-radius: 50%;
  background: var(--bronze);
  opacity: 0.8;
}

.hero-content {
  position: relative;
  z-index: 1;
}

.hero-inner {
  padding-bottom: 5rem;
}

@media (min-width: 1024px) {
  .hero-inner {
    padding-bottom: 7rem;
  }
}

.hero-eyebrow {
  display: flex;
  align-items: center;
  gap: 1rem;
  font-size: 0.62rem;
  letter-spacing: 0.28em;
  text-transform: uppercase;
  color: var(--bronze);
  margin-bottom: 1.75rem;
}

.eyebrow-line {
  display: block;
  width: 2.5rem;
  height: 1px;
  background: var(--bronze);
  opacity: 0.5;
}

.hero-headline {
  font-family: 'Playfair', Georgia, serif;
  font-size: clamp(2.8rem, 6.5vw, 6rem);
  line-height: 1.04;
  color: var(--text);
  margin-bottom: 2.5rem;
  letter-spacing: -0.01em;
}

.hero-headline em {
  font-style: italic;
  color: rgba(26, 25, 23, 0.5);
}

.hero-actions {
  display: flex;
  align-items: center;
  gap: 2rem;
  flex-wrap: wrap;
}

.hero-btn-primary {
  display: inline-block;
  background: var(--bronze);
  color: #fff;
  font-size: 0.65rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  font-weight: 600;
  padding: 1rem 2.25rem;
  transition: background 0.25s;
}

.hero-btn-primary:hover {
  background: #d9ba82;
}

.hero-btn-secondary {
  display: inline-flex;
  align-items: center;
  gap: 0.65rem;
  font-size: 0.65rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  color: rgba(26, 25, 23, 0.5);
  transition: color 0.2s;
}

.hero-btn-secondary:hover {
  color: var(--text);
}

.btn-arrow {
  font-size: 0.85rem;
  transition: transform 0.2s;
}

.hero-btn-secondary:hover .btn-arrow {
  transform: translateX(4px);
}

.scroll-indicator {
  position: absolute;
  bottom: 2.5rem;
  right: 2rem;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  z-index: 1;
}

.scroll-line {
  width: 1px;
  height: 56px;
  background: rgba(26, 25, 23, 0.12);
  position: relative;
  overflow: hidden;
}

.scroll-fill {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 50%;
  background: rgba(201, 169, 110, 0.6);
  animation: scrollDown 2s ease-in-out infinite;
}

@keyframes scrollDown {
  0% {
    transform: translateY(-100%);
  }

  100% {
    transform: translateY(200%);
  }
}
</style>
