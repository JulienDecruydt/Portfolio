<template>
  <section id="about" class="about">
    <div class="container">
      <!-- Section Header -->
      <div class="about__header">
        <h1 class="about__label">ABOUT ME</h1>
        <h2 class="about__title">
          {{ yearsOfExperience }}+ years of Vue.js experience enable me to respond quickly to <span class="text-gradient">YOUR NEEDS</span>
        </h2>
      </div>

      <!-- Content -->
      <div class="about__content">
        <p class="about__text">
          Since 2018, I've been working with Vue.js and Nuxt.js, and this experience has helped me develop my skills and grow my knowledge in these frameworks.
        </p>
        <p class="about__text">
          I have a passion for creating beautiful, performant websites and applications that deliver exceptional user experiences. As a professional developer, I'm always looking for new challenges and opportunities to push the boundaries of what's possible with modern web technologies.
        </p>
        <p class="about__highlight">
          Ready to bring your vision to life?
        </p>
        
        <!-- Social Links -->
        <div class="about__social">
          <a href="https://github.com/JulienDecruydt" target="_blank" class="about__social-link">
            <Icon name="lucide:github" />
          </a>
          <a href="https://www.linkedin.com/in/julien-decruydt/" target="_blank" class="about__social-link">
            <Icon name="lucide:linkedin" />
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const yearsOfExperience = new Date().getFullYear() - 2018
</script>

<style lang="scss" scoped>
.about {
  position: relative;
  padding: 8rem 0;
  background: #fafafa;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
}

.about__header {
  margin-bottom: 3rem;
}

.about__label {
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

.about__title {
  font-size: clamp(1.75rem, 4vw, 2.5rem);
  font-weight: 700;
  line-height: 1.2;
  color: #111827;

  span:first-child {
    color: #111827;
  }
}

.text-gradient {
  background: linear-gradient(135deg, #8b5cf6 0%, #d946ef 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.about__content {
  max-width: 720px;
}

.about__text {
  font-size: 1.125rem;
  color: #4b5563;
  line-height: 1.8;
  margin-bottom: 1.5rem;
}

.about__highlight {
  font-size: 1.125rem;
  font-weight: 600;
  color: #111827;
  margin-bottom: 2rem;
}

.about__social {
  display: flex;
  gap: 0.75rem;
}

.about__social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 48px;
  height: 48px;
  background: #ffffff;
  border: 1px solid #e5e7eb;
  border-radius: 12px;
  color: #6b7280;
  transition: all 0.3s ease;
  text-decoration: none;

  :deep(svg) {
    width: 20px;
    height: 20px;
  }

  &:hover {
    color: #8b5cf6;
    border-color: #c4b5fd;
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(139, 92, 246, 0.15);
  }
}
</style>
