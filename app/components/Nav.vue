<template>
  <nav 
    class="nav"
    :class="{ 'nav--scrolled': isScrolled }"
  >
    <div class="nav__container container">
      <!-- Logo -->
      <NuxtLink to="/" class="nav__logo">
        DECRUYDT
      </NuxtLink>

      <!-- Desktop Navigation -->
      <div class="nav__menu">
        <a 
          v-for="item in navItems" 
          :key="item.name"
          :href="item.href"
          class="nav__link"
        >
          {{ item.name }}
        </a>
      </div>

      <!-- CTA Button -->
      <a href="#contact" class="nav__cta btn btn--primary btn--sm">
        Get in touch
      </a>

      <!-- Mobile Menu Button -->
      <button 
        class="nav__toggle"
        :aria-expanded="isMenuOpen"
        aria-label="Toggle menu"
        @click="isMenuOpen = !isMenuOpen"
      >
        <span class="nav__toggle-line" :class="{ 'active': isMenuOpen }"></span>
      </button>
    </div>

    <!-- Mobile Menu -->
    <Transition name="mobile-menu">
      <div v-if="isMenuOpen" class="nav__mobile">
        <div class="nav__mobile-content">
          <a 
            v-for="item in navItems" 
            :key="item.name"
            :href="item.href"
            class="nav__mobile-link"
            @click="isMenuOpen = false"
          >
            {{ item.name }}
          </a>
          <a 
            href="#contact" 
            class="btn btn--primary btn--lg nav__mobile-cta"
            @click="isMenuOpen = false"
          >
            Get in touch
          </a>
        </div>
      </div>
    </Transition>
  </nav>
</template>

<script lang="ts" setup>
const isMenuOpen = ref(false)
const isScrolled = ref(false)

const navItems = [
  { name: 'About', href: '#about' },
  { name: 'Skills', href: '#skills' },
  { name: 'Projects', href: '#projects' },
]

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll, { passive: true })
  handleScroll()
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})

// Close mobile menu on escape
onMounted(() => {
  const handleEscape = (e: KeyboardEvent) => {
    if (e.key === 'Escape') isMenuOpen.value = false
  }
  window.addEventListener('keydown', handleEscape)
  onUnmounted(() => window.removeEventListener('keydown', handleEscape))
})
</script>

<style lang="scss" scoped>
.nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: var(--z-fixed);
  padding: var(--space-4) 0;
  transition: all var(--transition-base);


  &--scrolled {
    background: rgba(255, 255, 255, 0.85);
    backdrop-filter: blur(12px) saturate(180%);
    border-bottom: 1px solid var(--border-light);
    padding: var(--space-3) 0;
  }

  &__container {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  &__logo {
    font-size: var(--text-lg);
    font-weight: 600;
    color: var(--text-primary);
    text-decoration: none;
    letter-spacing: var(--tracking-tight);
    transition: color var(--transition-fast);

    &:hover {
      color: var(--color-primary-600);
    }
  }

  &__menu {
    display: none;
    align-items: center;
    gap: var(--space-8);

    @media (min-width: 768px) {
      display: flex;
    }
  }

  &__link {
    font-size: var(--text-sm);
    font-weight: 500;
    color: var(--text-secondary);
    text-decoration: none;
    transition: color var(--transition-fast);
    position: relative;

    &::after {
      content: '';
      position: absolute;
      bottom: -4px;
      left: 0;
      width: 0;
      height: 2px;
      background: var(--color-primary-500);
      border-radius: 1px;
      transition: width var(--transition-base);
    }

    &:hover {
      color: var(--text-primary);

      &::after {
        width: 100%;
      }
    }
  }

  &__cta {
    display: none;

    @media (min-width: 768px) {
      display: inline-flex;
    }
  }

  &__toggle {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 44px;
    height: 44px;
    background: transparent;
    border: none;
    cursor: pointer;
    position: relative;
    z-index: calc(var(--z-modal) + 1);

    @media (min-width: 768px) {
      display: none;
    }
  }

  &__toggle-line {
    width: 20px;
    height: 2px;
    background: var(--text-primary);
    border-radius: 1px;
    position: relative;
    transition: background var(--transition-fast);

    &::before,
    &::after {
      content: '';
      position: absolute;
      left: 0;
      width: 100%;
      height: 2px;
      background: var(--text-primary);
      border-radius: 1px;
      transition: transform var(--transition-base);
    }

    &::before {
      top: -6px;
    }

    &::after {
      top: 6px;
    }

    &.active {
      background: transparent;

      &::before {
        transform: translateY(6px) rotate(45deg);
      }

      &::after {
        transform: translateY(-6px) rotate(-45deg);
      }
    }
  }

  &__mobile {
    position: fixed;
    inset: 0;
    background: var(--bg-primary);
    z-index: var(--z-modal);
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;

    @media (min-width: 768px) {
      display: none;
    }
  }

  &__mobile-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: var(--space-6);
  }

  &__mobile-link {
    font-size: var(--text-2xl);
    font-weight: 500;
    color: var(--text-primary);
    text-decoration: none;
    transition: color var(--transition-fast);

    &:hover {
      color: var(--color-primary-600);
    }
  }

  &__mobile-cta {
    margin-top: var(--space-4);
  }
}

// Mobile menu transitions
.mobile-menu-enter-active,
.mobile-menu-leave-active {
  transition: opacity var(--transition-slow);
}

.mobile-menu-enter-from,
.mobile-menu-leave-to {
  opacity: 0;
}

// Button styles (shared)
.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-family: inherit;
  font-weight: 500;
  text-decoration: none;
  border: none;
  cursor: pointer;
  transition: all var(--transition-base);
  white-space: nowrap;

  &--sm {
    height: var(--btn-height-sm);
    padding: 0 var(--btn-padding-x-sm);
    font-size: var(--btn-font-size-sm);
    border-radius: var(--radius-md);
  }

  &--md {
    height: var(--btn-height-md);
    padding: 0 var(--btn-padding-x-md);
    font-size: var(--btn-font-size-md);
    border-radius: var(--radius-md);
  }

  &--lg {
    height: var(--btn-height-lg);
    padding: 0 var(--btn-padding-x-lg);
    font-size: var(--btn-font-size-lg);
    border-radius: var(--radius-lg);
  }

  &--primary {
    background: var(--gradient-primary);
    color: white;
    box-shadow: var(--shadow-primary);

    &:hover {
      transform: translateY(-1px);
      box-shadow: var(--shadow-primary-lg);
    }

    &:active {
      transform: translateY(0);
    }
  }

  &--secondary {
    background: var(--bg-secondary);
    color: var(--text-primary);
    border: 1px solid var(--border-light);

    &:hover {
      background: var(--bg-tertiary);
      border-color: var(--border-medium);
    }
  }
}
</style>
