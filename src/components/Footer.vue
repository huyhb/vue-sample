<template>
  <footer class="app-footer">
    <div class="footer-content">
      <p>© 2025 YourCompany. All rights reserved.</p>
      <nav>
        <a href="#">Privacy</a>
        <a href="#">Terms</a>
        <a href="#">Contact</a>
      </nav>
    </div>
  </footer>
</template>

<script setup>
// không cần gì đặc biệt
</script>

<style scoped>
@media (min-width: 1024px) {
  body {
    display: flex;
    place-items: center;
  }
}


.app-footer {
  padding: 1.5rem;
  background-color: var(--color-background-soft);
  color: var(--color-text);
  border-top: 1px solid var(--color-border);
  text-align: center;
  font-size: 0.9rem;
}

.footer-content {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  align-items: center;
}

.footer-content nav {
  display: flex;
  gap: 1.5rem;
}

.footer-content a {
  color: var(--color-text);
  text-decoration: none;
  font-weight: 500;
}

.footer-content a:hover {
  color: var(--color-heading);
  text-decoration: underline;
}
</style>
