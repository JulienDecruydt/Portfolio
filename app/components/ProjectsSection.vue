<template>
  <section id="projects" class="projects">
    <div class="container">
      <!-- Section Header -->
      <div class="projects__header">
        <h1 class="projects__label">MY WORK</h1>
        <h2 class="projects__title">
          <span>Featured</span> <span class="text-gradient">Projects</span>
        </h2>
        <p class="projects__subtitle">
          Here are some of the projects I've worked on, showcasing my expertise in Vue.js, Nuxt.js, and modern web development.
        </p>
      </div>

      <!-- Projects Grid -->
      <div class="projects__grid">
        <div
          v-for="(project, index) in projects" 
          :key="project.name + index"
          class="project-card"
        >
          <!-- Content -->
          <div class="project-card__content">
            <!-- Header -->
            <div class="project-card__header">
              <div class="project-card__company">{{ project.company }}</div>
              <div class="project-card__year">{{ project.year }}</div>
            </div>
            
            <!-- Main Info -->
            <div class="project-card__main">
              <h3 class="project-card__title">{{ project.name }}</h3>                            
              <p class="project-card__desc">{{ project.description }}</p>
            </div>
            
            <!-- Footer -->
            <div class="project-card__footer">
              <div class="project-card__tags">
                <span class="project-card__tag" v-for="tag in project.tags" :key="tag">{{ tag }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const projects = [
  {
    name: 'Suzuki France',
    company: 'Suzuki',
    description: 'Official website for Suzuki France with modern design, vehicle catalog, and dealer locator functionality.',
    year: '2022',
    tags: ['Vue.js', 'Nuxt.js', 'Tailwind CSS']
  },
  {
    name: 'Suzuki Concession',
    company: 'Suzuki',
    description: 'Website for Suzuki dealers of Suzuki cars.',
    year: '2022',
    tags: ['Vue.js', 'Nuxt.js', 'Tailwind CSS']
  },
  {
    name: 'Suzuki Care',
    company: 'Suzuki',
    description: 'Digital platform for dealerships to manage service estimates, repairs, and maintenance scheduling efficiently.',
    year: '2023',
    tags: ['Vue.js', 'Nuxt.js', 'Tailwind CSS']
  },
  {
    name: 'Novaseo',
    company: 'Novaseo',
    description: 'SaaS platform providing comprehensive SEO tools and analytics for their clients.',
    year: '2018',
    tags: ['Vue.js', 'Python', 'Django', 'Tailwind CSS']
  },
  {
    name: 'Novavocat',
    company: 'Novaseo',
    description: 'Legal consultation platform connecting clients with qualified lawyers through an intuitive Q&A system.',
    year: '2019',
    tags: ['Vue.js', 'Nuxt.js', 'Django', 'Tailwind CSS']
  },
  {
    name: 'Quai38',
    company: 'Quai38',
    description: 'Restaurant website featuring menu showcase, reservation system, and location information.',
    year: '2018',
    tags: ['Vue.js', 'Nuxt.js', 'Sass']
  }
]
</script>

<style lang="scss" scoped>
.projects {
  position: relative;
  padding: 8rem 0;
  background: #fafafa;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
}

.projects__header {
  margin-bottom: 4rem;
}

.projects__label {
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

.projects__title {
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

.projects__subtitle {
  font-size: 1rem;
  color: #6b7280;
  max-width: 600px;
  line-height: 1.6;
}

.projects__grid {
  display: grid;
  gap: 1.5rem;
  margin-bottom: 4rem;

  @media (min-width: 768px) {
    grid-template-columns: repeat(2, 1fr);
  }

  @media (min-width: 1024px) {
    grid-template-columns: repeat(3, 1fr);
  }
}

.project-card {
  background: #ffffff;
  border: 1px solid #e5e7eb;
  border-radius: 16px;
  overflow: hidden;
  transition: all 0.3s ease;
  min-height: 280px;

  &:hover {
    transform: translateY(-8px);
    border-color: #c4b5fd;
    box-shadow: 0 20px 40px rgba(139, 92, 246, 0.1);

    .project-card__title {
      color: #8b5cf6;
    }
  }

  &__content {
    padding: 1.5rem;
    height: 100%;
    display: flex;
    flex-direction: column;
  }

  &__header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
  }

  &__company {
    font-size: 0.875rem;
    font-weight: 600;
    color: #8b5cf6;
  }

  &__year {
    background: #f3f4f6;
    color: #6b7280;
    font-size: 0.75rem;
    font-weight: 500;
    padding: 0.25rem 0.75rem;
    border-radius: 12px;
  }

  &__main {
    flex: 1;
    margin-bottom: 1.5rem;
  }

  &__title {
    font-size: 1.125rem;
    font-weight: 700;
    color: #111827;
    margin-bottom: 0.75rem;
    line-height: 1.4;
    transition: color 0.3s ease;
  }

  &__desc {
    color: #6b7280;
    font-size: 0.875rem;
    line-height: 1.6;
  }

  &__footer {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  &__tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  &__tag {
    background: #f3f4f6;
    color: #4b5563;
    font-size: 0.75rem;
    font-weight: 500;
    padding: 0.25rem 0.75rem;
    border-radius: 8px;
  }
}

.projects__cta {
  text-align: center;
}

.projects__cta-text {
  color: #6b7280;
  margin-bottom: 1.5rem;
}

.projects__cta-btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: linear-gradient(135deg, #8b5cf6 0%, #d946ef 100%);
  color: #ffffff;
  padding: 14px 28px;
  border-radius: 12px;
  text-decoration: none;
  font-weight: 600;
  font-size: 14px;
  transition: all 0.3s ease;
  box-shadow: 0 8px 24px rgba(139, 92, 246, 0.3);

  &:hover {
    transform: translateY(-2px);
    box-shadow: 0 12px 32px rgba(139, 92, 246, 0.4);
  }

  .projects__cta-icon {
    width: 1rem;
    height: 1rem;
  }
}
</style>
