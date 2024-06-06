<template>
  <div class="watermark">
    <header class="flex-center">
      <img src="@/assets/images/logo.svg">
      <h2 class="text">ComputeSphere</h2>
    </header>
    <div class="container flex-center">
      <p class="logo-text">Welcome to <span class="logo-gradient">ComputeSphere</span></p>

      <CountdownTimer />
      <br>
      <a class="text link" href="https://docs.computesphere.com/">Explore our documentation</a>
      <a class="text link" href="https://support.computesphere.com/">Reach out to support</a>
    </div>
    <footer class="flex-center">
      <p>Copyright &copy; <span id="currentYear">{{ new Date().getFullYear() }}</span> ComputeSphere LLC</p>
      <div class="footer-links">
        All Rights Reserved |
        <a class="text link" href="https://computesphere.com/">Terms & Conditions |</a>
        <a class="text link" href="https://computesphere.com/">Privacy Policy</a>
      </div>
    </footer>
  </div>
</template>

<script setup>
import CountdownTimer from '@/components/CountdownTimer.vue'

</script>

<style lang="scss" scoped></style>
