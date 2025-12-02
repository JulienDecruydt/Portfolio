<template>
  <footer class="footer">
    <div class="container">
      <div class="footer__content">
        <span class="footer__copy">© {{ currentYear }} Julien Decruydt</span>
        <span class="footer__divider">·</span>
        <span class="footer__role">Vue.js Developer</span>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
const currentYear = new Date().getFullYear()
</script>

<style lang="scss" scoped>
.footer {
  padding: 2rem 0;
  background: #fafafa;
  border-top: 1px solid #e5e7eb;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
}

.footer__content {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.75rem;
  font-size: 14px;
  color: #6b7280;
}

.footer__divider {
  opacity: 0.5;
}
</style>
