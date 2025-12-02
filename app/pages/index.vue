<template>
  <div>
    <Heading />
    <AboutSection />
    <SkillsSection />
    <ProjectsSection />
    <ContactSection />
    <AppFooter />
  </div>
</template>

<script setup lang="ts">
useHead({
  title: 'Julien Decruydt — Vue.js Developer',
  meta: [
    { 
      name: 'description', 
      content: 'Vue.js & Nuxt.js developer with 6+ years of experience. Building modern, performant web applications.' 
    },
    { 
      property: 'og:title', 
      content: 'Julien Decruydt — Vue.js Developer' 
    },
    { 
      property: 'og:description', 
      content: 'Vue.js & Nuxt.js developer with 6+ years of experience. Building modern, performant web applications.' 
    },
  ]
})
</script>
