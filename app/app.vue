<template>
  <div class="app">
    <Nav />
    <main>
      <NuxtPage />
    </main>
  </div>
</template>

<style lang="scss">
// All base styles are now in design-system.scss
// This file only contains app-specific overrides if needed

::selection {
  background: var(--color-primary-200);
  color: var(--color-primary-900);
}

// Smooth focus styles
:focus-visible {
  outline: 2px solid var(--color-primary-500);
  outline-offset: 2px;
}

// Remove default focus for mouse users
:focus:not(:focus-visible) {
  outline: none;
}
</style>
