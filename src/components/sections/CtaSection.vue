<script setup lang="ts">
import { ref } from 'vue'

const form = ref({
  name: '',
  email: '',
  service: '',
  message: '',
  honeypot: '',
})

const submitted = ref(false)

function handleSubmit() {
  if (form.value.honeypot) return
  submitted.value = true
}
</script>

<template>
  <section id="contact" class="cta-section">
    <div class="container">
      <div class="cta-grid">
        <!-- Left: headline + contact info -->
        <div class="cta-left">
          <p class="section-label">Get In Touch</p>
          <h2 class="cta-headline">
            The perfect shot<br /><em>is just a<br />conversation away.</em>
          </h2>

          <div class="contact-details">
            <a href="mailto:info@aikyphotography.com" class="contact-link">
              info@aikyphotography.com
            </a>
            <a href="tel:5134613086" class="contact-link">
              (513) 461-3086
            </a>
            <p class="contact-address">Oxford, OH 45056</p>
          </div>
        </div>

        <!-- Right: form -->
        <div class="cta-right">
          <div v-if="submitted" class="submitted-state">
            <p class="section-label">Message Sent</p>
            <p class="submitted-message">
              Thank you. We'll be in touch shortly.
            </p>
          </div>

          <form v-else @submit.prevent="handleSubmit" class="contact-form">
            <!-- Honeypot -->
            <input
              v-model="form.honeypot"
              type="text"
              name="website"
              tabindex="-1"
              autocomplete="off"
              class="hidden"
              aria-hidden="true"
            />

            <div class="form-row">
              <div class="form-field">
                <label class="form-label">Full Name</label>
                <input
                  v-model="form.name"
                  type="text"
                  required
                  placeholder="Jane Doe"
                  class="form-input"
                />
              </div>

              <div class="form-field">
                <label class="form-label">Email</label>
                <input
                  v-model="form.email"
                  type="email"
                  required
                  placeholder="jane@brand.com"
                  class="form-input"
                />
              </div>
            </div>

            <div class="form-field">
              <label class="form-label">Service</label>
              <select v-model="form.service" class="form-input form-select">
                <option value="" disabled>Select a service</option>
                <option>Fashion &amp; Editorial</option>
                <option>Brand &amp; Commercial</option>
                <option>Portrait &amp; Studio</option>
                <option>Other</option>
              </select>
            </div>

            <div class="form-field">
              <label class="form-label">Message</label>
              <textarea
                v-model="form.message"
                required
                rows="4"
                placeholder="Tell us about your project..."
                class="form-input form-textarea"
              ></textarea>
            </div>

            <div class="form-submit">
              <button type="submit" class="submit-btn">
                Send Message
              </button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.cta-section {
  background: var(--bg-alt);
  padding: 8rem 0;
  border-top: 1px solid var(--divider);
}

.cta-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 5rem;
}

@media (min-width: 1024px) {
  .cta-grid {
    grid-template-columns: 1fr 1fr;
    gap: 6rem;
    align-items: start;
  }
}

.section-label {
  font-size: 0.62rem;
  letter-spacing: 0.28em;
  text-transform: uppercase;
  color: var(--bronze);
  margin-bottom: 1.25rem;
}

.cta-headline {
  font-family: 'Playfair', Georgia, serif;
  font-size: clamp(2.2rem, 4vw, 3.75rem);
  color: var(--text);
  line-height: 1.1;
  margin-bottom: 2.5rem;
  letter-spacing: -0.01em;
}

.cta-headline em {
  font-style: italic;
  color: var(--text-muted);
}

.contact-details {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.contact-link {
  font-size: 0.875rem;
  color: var(--text-muted);
  transition: color 0.2s;
}

.contact-link:hover {
  color: var(--bronze);
}

.contact-address {
  font-size: 0.875rem;
  color: var(--text-muted);
  opacity: 0.6;
}

.submitted-state {
  display: flex;
  flex-direction: column;
  justify-content: center;
  min-height: 300px;
}

.submitted-message {
  font-family: 'Playfair', Georgia, serif;
  font-size: 1.5rem;
  color: var(--text);
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.75rem;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1.75rem;
}

@media (min-width: 640px) {
  .form-row {
    grid-template-columns: 1fr 1fr;
  }
}

.form-field {
  display: flex;
  flex-direction: column;
  gap: 0.6rem;
}

.form-label {
  font-size: 0.6rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  color: var(--text-muted);
  opacity: 0.7;
}

.form-input {
  border: none;
  border-bottom: 1px solid var(--divider-mid);
  padding: 0.75rem 0;
  font-size: 0.875rem;
  color: var(--text);
  background: transparent;
  outline: none;
  transition: border-color 0.2s;
  font-family: inherit;
  width: 100%;
}

.form-input::placeholder {
  color: var(--text-muted);
  opacity: 0.4;
}

.form-input:focus {
  border-bottom-color: var(--bronze);
}

.form-select {
  appearance: none;
  cursor: pointer;
  color: var(--text-muted);
}

.form-select option {
  background: var(--bg);
  color: var(--text);
}

.form-textarea {
  resize: none;
  line-height: 1.6;
}

.form-submit {
  padding-top: 0.5rem;
}

.submit-btn {
  background: var(--bronze);
  color: var(--ink);
  font-size: 0.65rem;
  letter-spacing: 0.22em;
  text-transform: uppercase;
  font-weight: 600;
  padding: 1rem 2.5rem;
  border: none;
  cursor: pointer;
  transition: background 0.25s;
  font-family: inherit;
}

.submit-btn:hover {
  background: #d9ba82;
}
</style>
