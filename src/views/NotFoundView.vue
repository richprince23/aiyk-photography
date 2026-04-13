<template>
  <main class="not-found">
    <div class="container not-found-inner">
      <p class="not-found-label">404</p>
      <h1 class="not-found-headline">
        Page not<br /><em>found.</em>
      </h1>
      <p class="not-found-body">
        The page you're looking for doesn't exist or has been moved.
      </p>
      <RouterLink to="/" class="not-found-btn">Back to Home</RouterLink>
    </div>
  </main>
</template>

<style scoped>
.not-found {
  min-height: calc(100svh - 80px);
  display: flex;
  align-items: center;
  background: var(--bg);
}

.not-found-inner {
  padding-top: 6rem;
  padding-bottom: 6rem;
}

.not-found-label {
  font-size: 0.62rem;
  letter-spacing: 0.28em;
  text-transform: uppercase;
  color: var(--bronze);
  margin-bottom: 1.75rem;
}

.not-found-headline {
  font-family: 'Playfair', Georgia, serif;
  font-size: clamp(3rem, 8vw, 7rem);
  line-height: 1.04;
  color: var(--text);
  letter-spacing: -0.01em;
  margin-bottom: 2rem;
}

.not-found-headline em {
  font-style: italic;
  color: rgba(26, 25, 23, 0.5);
}

.not-found-body {
  font-size: 0.95rem;
  color: var(--text-muted);
  line-height: 1.75;
  max-width: 26rem;
  margin-bottom: 3rem;
}

.not-found-btn {
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

.not-found-btn:hover {
  background: #d9ba82;
}
</style>
