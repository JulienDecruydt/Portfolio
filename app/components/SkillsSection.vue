<template>
  <section class="skills" id="skills">
    <div class="container">
      <!-- Section Header -->
      <div class="skills__header">
        <h1 class="skills__label">MY EXPERTISE</h1>
        <h2 class="skills__title">
          <span>Skills &</span> <span class="text-gradient">Technologies</span>
        </h2>
        <p class="skills__subtitle">
          High-level experience with Vue.js, Nuxt.js, and modern JavaScript ecosystem to deliver exceptional solutions quickly.
        </p>
      </div>

      <!-- Skills Grid -->
      <div class="skills__grid">
        <div 
          v-for="skill in skills" 
          :key="skill.name"
          class="skill-card"
        >
          <div class="skill-card__icon">
            <Icon :name="skill.icon" />
          </div>
          <h3 class="skill-card__name">{{ skill.name }}</h3>
          <p class="skill-card__desc">{{ skill.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const skills = [
  {
    name: 'Vue.js',
    icon: 'simple-icons:vuedotjs',
    description: 'Advanced proficiency in Vue.js ecosystem and best practices'
  },
  {
    name: 'Nuxt.js',
    icon: 'simple-icons:nuxtdotjs',
    description: 'Expert in building SSR and SPA applications'
  },
  {
    name: 'JavaScript',
    icon: 'simple-icons:javascript',
    description: 'Modern ES6+ JavaScript and TypeScript'
  },
  {
    name: 'TypeScript',
    icon: 'simple-icons:typescript',
    description: 'Strong typing for JavaScript'
  },
  {
    name: 'Pinia',
    icon: 'simple-icons:pinia',
    description: 'Typescript state management for Vue.js'
  },
  {
    name: 'Tailwind CSS',
    icon: 'simple-icons:tailwindcss',
    description: 'Utility-first CSS framework for rapid UI development'
  },
  {
    name: 'Sass/SCSS',
    icon: 'simple-icons:sass',
    description: 'Advanced CSS preprocessing and architecture'
  },
  {
    name: 'Git',
    icon: 'simple-icons:git',
    description: 'Version control and collaborative development'
  },
  {
    name: 'Ionic',
    icon: 'simple-icons:ionic',
    description: 'Cross-platform mobile app development'
  },
  {
    name: 'Python',
    icon: 'simple-icons:python',
    description: 'Backend development and automation scripts'
  },
  {
    name: 'React',
    icon: 'simple-icons:react',
    description: 'Frontend framework for building web applications'
  },
  {
    name: 'Prisma',
    icon: 'simple-icons:prisma',
    description: 'ORM for database management'
  },
  {
    name: 'PostgreSQL',
    icon: 'simple-icons:postgresql',
    description: 'Relational database management system'
  },
]
</script>

<style lang="scss" scoped>
.skills {
  position: relative;
  padding: 8rem 0;
  background: #ffffff;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
}

.skills__header {
  margin-bottom: 4rem;
}

.skills__label {
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

.skills__title {
  font-size: clamp(1.75rem, 4vw, 2.5rem);
  font-weight: 700;
  line-height: 1.2;
  margin-bottom: 1rem;

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

.skills__subtitle {
  font-size: 1rem;
  color: #6b7280;
  max-width: 600px;
  line-height: 1.6;
}

.skills__grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem;

  @media (min-width: 768px) {
    grid-template-columns: repeat(4, 1fr);
  }
}

.skill-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: 2rem 1.5rem;
  background: #fafafa;
  border: 1px solid #e5e7eb;
  border-radius: 16px;
  transition: all 0.3s ease;

  &:hover {
    transform: translateY(-8px);
    border-color: #c4b5fd;
    background: #ffffff;
    box-shadow: 0 20px 40px rgba(139, 92, 246, 0.1);

    .skill-card__icon {
      transform: scale(1.15);
      color: #8b5cf6;
    }

    .skill-card__name {
      color: #8b5cf6;
    }
  }

  &__icon {
    font-size: 2rem;
    color: #374151;
    transition: all 0.3s ease;
    margin-bottom: 1rem;

    :deep(svg) {
      width: 2rem;
      height: 2rem;
    }
  }

  &__name {
    font-size: 1rem;
    font-weight: 600;
    color: #111827;
    margin-bottom: 0.5rem;
    transition: color 0.3s ease;
  }

  &__desc {
    color: #6b7280;
    font-size: 0.85rem;
    line-height: 1.5;
  }
}
</style>
