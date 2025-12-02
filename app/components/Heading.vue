<template>
  <section class="hero">
    <!-- Animated background blobs -->
    <div class="hero__blobs" aria-hidden="true">
      <div class="hero__blob hero__blob--1"></div>
      <div class="hero__blob hero__blob--2"></div>
      <div class="hero__blob hero__blob--3"></div>
    </div>

    <!-- Grid pattern overlay -->
    <div class="hero__grid" aria-hidden="true"></div>

    <div class="hero__container container">
      <!-- Floating availability pill -->
      <div class="hero__status">
        <span class="hero__status-dot"></span>
        <span>Open to work</span>
      </div>

      <!-- Giant headline with split design -->
      <div class="hero__headline">
        <span class="hero__line">Your next project needs a</span>
        <span class="hero__line">
          <span class="text-gradient">Vue.js</span> developer
        </span>
      </div>

      <!-- Minimal tagline -->
      <p class="hero__tag">Let's work together to create exceptional projects.</p>

      <!-- CTAs -->
      <div class="hero__ctas">
        <a href="#projects" class="hero__cta hero__cta--primary">
          <span>Discover my work</span>
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M7 17L17 7M17 7H7M17 7V17"/>
          </svg>
        </a>
        <a href="#about" class="hero__cta hero__cta--secondary">
          <span>Learn more</span>
        </a>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup>
</script>

<style lang="scss" scoped>
.hero {
  position: relative;
  min-height: 100vh;
  min-height: 100dvh;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  background: #ffffff;

  // Animated gradient blobs
  &__blobs {
    position: absolute;
    inset: 0;
    overflow: hidden;
    pointer-events: none;
  }

  &__blob {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.5;
    animation: float 20s ease-in-out infinite;

    &--1 {
      width: 600px;
      height: 600px;
      background: linear-gradient(135deg, rgba(139, 92, 246, 0.3) 0%, rgba(217, 70, 239, 0.15) 100%);
      top: -20%;
      right: -10%;
      animation-delay: 0s;
    }

    &--2 {
      width: 500px;
      height: 500px;
      background: linear-gradient(135deg, rgba(59, 130, 246, 0.2) 0%, rgba(139, 92, 246, 0.15) 100%);
      bottom: -15%;
      left: -10%;
      animation-delay: -7s;
    }

    &--3 {
      width: 300px;
      height: 300px;
      background: linear-gradient(135deg, rgba(236, 72, 153, 0.2) 0%, rgba(139, 92, 246, 0.1) 100%);
      top: 40%;
      left: 50%;
      animation-delay: -14s;
    }
  }

  // Subtle grid
  &__grid {
    position: absolute;
    inset: 0;
    background-image: 
      linear-gradient(rgba(139, 92, 246, 0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(139, 92, 246, 0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    mask-image: radial-gradient(ellipse 60% 60% at 50% 50%, black 20%, transparent 70%);
  }

  &__container {
    position: relative;
    z-index: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding: 6rem 24px;
    max-width: 1200px;
    margin: 0 auto;
  }

  // Status badge
  &__status {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 16px;
    background: rgba(16, 185, 129, 0.1);
    border: 1px solid rgba(16, 185, 129, 0.2);
    border-radius: 50px;
    font-size: 13px;
    font-weight: 500;
    color: #059669;
    margin-bottom: 3rem;
  }

  &__status-dot {
    width: 8px;
    height: 8px;
    background: #10b981;
    border-radius: 50%;
    animation: blink 2s ease-in-out infinite;
  }

  // Giant headline
  &__headline {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 1.5rem;
  }

  &__line {
    font-size: clamp(2.5rem, 10vw, 6rem);
    font-weight: 700;
    line-height: 1.1;
    letter-spacing: -0.03em;
    color: #111827;

    .text-gradient {
      background: linear-gradient(135deg, #8b5cf6 0%, #d946ef 50%, #8b5cf6 100%);
      background-size: 200% auto;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      animation: shimmer 3s linear infinite;
    }
  }

  // Tagline
  &__tag {
    font-size: 1.125rem;
    font-weight: 400;
    color: #6b7280;
    letter-spacing: 0.01em;
    margin-bottom: 2.5rem;
    max-width: 500px;

    @media (min-width: 768px) {
      font-size: 1.25rem;
    }
  }

  // CTAs
  &__ctas {
    display: flex;
    flex-direction: column;
    gap: 1rem;

    @media (min-width: 640px) {
      flex-direction: row;
    }
  }

  &__cta {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    padding: 16px 28px;
    font-size: 15px;
    font-weight: 500;
    text-decoration: none;
    border-radius: 50px;
    transition: all 0.3s ease;

    svg {
      transition: transform 0.3s ease;
    }

    &--primary {
      background: #111827;
      color: #ffffff;
      box-shadow: 0 8px 24px rgba(17, 24, 39, 0.2);

      &:hover {
        transform: translateY(-2px);
        box-shadow: 0 12px 32px rgba(17, 24, 39, 0.25);

        svg {
          transform: translate(3px, -3px);
        }
      }
    }

    &--secondary {
      background: transparent;
      color: #374151;
      border: 1px solid #d1d5db;

      &:hover {
        background: #f9fafb;
        border-color: #9ca3af;
        transform: translateY(-2px);
      }
    }
  }

  // Scroll indicator
  &__scroll {
    position: absolute;
    bottom: 2rem;
    left: 50%;
    transform: translateX(-50%);
  }

  &__mouse {
    width: 24px;
    height: 38px;
    border: 2px solid #d1d5db;
    border-radius: 12px;
    display: flex;
    justify-content: center;
    padding-top: 6px;
  }

  &__wheel {
    width: 4px;
    height: 8px;
    background: #9ca3af;
    border-radius: 2px;
    animation: scroll 2s ease-in-out infinite;
  }
}

// Animations
@keyframes float {
  0%, 100% {
    transform: translate(0, 0) rotate(0deg);
  }
  33% {
    transform: translate(30px, -30px) rotate(5deg);
  }
  66% {
    transform: translate(-20px, 20px) rotate(-5deg);
  }
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.4; }
}

@keyframes shimmer {
  to { background-position: 200% center; }
}

@keyframes scroll {
  0%, 100% {
    transform: translateY(0);
    opacity: 1;
  }
  50% {
    transform: translateY(6px);
    opacity: 0.5;
  }
}
</style>
