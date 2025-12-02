<template>
  <section id="contact" class="contact">
    <!-- Subtle background gradient -->
    <div class="contact__bg" aria-hidden="true"></div>

    <div class="container">
      <div class="contact__content">
        <!-- Section Label -->
        <h1 class="contact__label">CONTACT</h1>

        <!-- Big headline -->
        <h2 class="contact__title">
          Interested in working together ? <span class="text-gradient">Let's talk.</span>
        </h2>

        <!-- Email button - main CTA -->
        <a href="mailto:juliendecruydt@gmail.com" class="contact__email">
          <span>juliendecruydt@gmail.com</span>
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M7 17L17 7M17 7H7M17 7V17"/>
          </svg>
        </a>

        <!-- Social links -->
        <div class="contact__socials">
          <a href="https://github.com/JulienDecruydt" target="_blank" class="contact__social">
            <Icon name="lucide:github" />
          </a>
          <a href="https://www.linkedin.com/in/julien-decruydt/" target="_blank" class="contact__social">
            <Icon name="lucide:linkedin" />
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style lang="scss" scoped>
.contact {
  position: relative;
  padding: 8rem 0;
  background: #ffffff;
  overflow: hidden;

  &__bg {
    position: absolute;
    inset: 0;
    background: 
      radial-gradient(circle at 20% 80%, rgba(139, 92, 246, 0.08) 0%, transparent 50%),
      radial-gradient(circle at 80% 20%, rgba(217, 70, 239, 0.06) 0%, transparent 50%);
    pointer-events: none;
  }
}

.container {
  position: relative;
  z-index: 1;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
}

.contact__content {
  text-align: center;
  max-width: 600px;
  margin: 0 auto;
}

.contact__label {
  font-size: 0.875rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  color: #6b7280;
  text-transform: uppercase;
  margin-bottom: 1rem;

  @media (min-width: 768px) {
    font-size: 1rem;
  }
}

.contact__title {
  font-size: clamp(2rem, 6vw, 3.5rem);
  font-weight: 700;
  line-height: 1.1;
  letter-spacing: -0.02em;
  color: #111827;
  margin-bottom: 1.5rem;
}

.text-gradient {
  background: linear-gradient(135deg, #8b5cf6 0%, #d946ef 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.contact__text {
  font-size: 1.125rem;
  color: #6b7280;
  margin-bottom: 2.5rem;
}

.contact__email {
  display: inline-flex;
  align-items: center;
  gap: 12px;
  padding: 18px 32px;
  background: #111827;
  color: #ffffff;
  font-size: 16px;
  font-weight: 500;
  text-decoration: none;
  border-radius: 50px;
  transition: all 0.3s ease;
  box-shadow: 0 8px 24px rgba(17, 24, 39, 0.2);
  margin-bottom: 2.5rem;

  svg {
    transition: transform 0.3s ease;
  }

  &:hover {
    transform: translateY(-2px);
    box-shadow: 0 12px 32px rgba(17, 24, 39, 0.25);

    svg {
      transform: translate(3px, -3px);
    }
  }
}

.contact__socials {
  display: flex;
  justify-content: center;
  gap: 0.75rem;
}

.contact__social {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 48px;
  height: 48px;
  background: #fafafa;
  border: 1px solid #e5e7eb;
  border-radius: 50%;
  color: #6b7280;
  transition: all 0.3s ease;
  text-decoration: none;

  :deep(svg) {
    width: 20px;
    height: 20px;
  }

  &:hover {
    border-color: #c4b5fd;
    color: #8b5cf6;
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(139, 92, 246, 0.15);
  }
}
</style>
