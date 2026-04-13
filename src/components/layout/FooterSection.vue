<template>
  <footer class="site-footer">
    <div class="container">
      <div class="footer-top">
        <!-- Brand -->
        <div class="footer-brand">
          <p class="footer-logo">aiky</p>
          <p class="footer-tagline">
            Professional commercial photography studio creating clean, strategic imagery for modern brands.
          </p>
        </div>

        <!-- Nav -->
        <div class="footer-col">
          <p class="footer-col-label">Navigation</p>
          <nav class="footer-nav">
            <a href="#home" class="footer-link">Home</a>
            <a href="#services" class="footer-link">Services</a>
            <a href="#portfolio" class="footer-link">Portfolio</a>
            <a href="#contact" class="footer-link">Contact</a>
          </nav>
        </div>

        <!-- Contact -->
        <div class="footer-col">
          <p class="footer-col-label">Contact</p>
          <div class="footer-contact">
            <a href="mailto:info@aikyphotography.com" class="footer-link">
              info@aikyphotography.com
            </a>
            <a href="tel:5134613086" class="footer-link">
              (513) 461-3086
            </a>
            <p class="footer-address">216 E Sycamore St Apt 9<br />Oxford, OH 45056</p>
          </div>
        </div>
      </div>

      <div class="footer-bottom">
        <p class="footer-copy">
          &copy; {{ new Date().getFullYear() }} aiky Photography. All rights reserved.
        </p>
        <p class="footer-copy">Oxford, OH</p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.site-footer {
  background: var(--bg-alt);
  border-top: 1px solid var(--divider);
  padding: 5rem 0 3rem;
}

.footer-top {
  display: grid;
  grid-template-columns: 1fr;
  gap: 3rem;
  margin-bottom: 4rem;
}

@media (min-width: 768px) {
  .footer-top {
    grid-template-columns: 5fr 3fr 4fr;
    gap: 3rem;
  }
}

.footer-logo {
  font-family: 'Playfair', Georgia, serif;
  font-size: 0.75rem;
  letter-spacing: 0.35em;
  text-transform: uppercase;
  color: var(--text);
  margin-bottom: 1.25rem;
}

.footer-tagline {
  font-size: 0.875rem;
  color: var(--text-muted);
  line-height: 1.7;
  max-width: 18rem;
  opacity: 0.7;
}

.footer-col-label {
  font-size: 0.58rem;
  letter-spacing: 0.28em;
  text-transform: uppercase;
  color: var(--bronze);
  opacity: 0.55;
  margin-bottom: 1.25rem;
}

.footer-nav,
.footer-contact {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.footer-link {
  font-size: 0.875rem;
  color: var(--text-muted);
  opacity: 0.7;
  transition: color 0.2s, opacity 0.2s;
}

.footer-link:hover {
  color: var(--text);
  opacity: 1;
}

.footer-address {
  font-size: 0.875rem;
  color: var(--text-muted);
  opacity: 0.45;
  line-height: 1.6;
}

.footer-bottom {
  border-top: 1px solid var(--divider);
  padding-top: 2rem;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

@media (min-width: 640px) {
  .footer-bottom {
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
  }
}

.footer-copy {
  font-size: 0.68rem;
  color: var(--text-muted);
  opacity: 0.45;
  letter-spacing: 0.05em;
}
</style>
