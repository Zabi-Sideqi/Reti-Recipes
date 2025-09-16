
<!-- src/components/ResponsiveNavbar.vue -->

<!--
<script setup lang="ts">
import { ref, watch, onMounted } from 'vue';
import { useRoute, useRouter } from 'vue-router';
import logoImg from '@/assets/img/logo.png';

const route = useRoute();
const router = useRouter();
const isMenuOpen = ref(false);

// Reaktiv variabel för inloggningsstatus
const isLoggedIn = ref(!!localStorage.getItem('authToken'));

function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value;
}

function closeMenu() {
  isMenuOpen.value = false;
}

function logout() {
  localStorage.removeItem('authToken');
  isLoggedIn.value = false; // Uppdatera inloggningsstatusen
  router.push('/');
  closeMenu();
}

// Uppdatera inloggningsstatus när komponenten laddas
onMounted(() => {
  isLoggedIn.value = !!localStorage.getItem('authToken');
});

// Stäng menyn när vi navigerar till en annan sida
watch(() => route.path, () => {
  closeMenu();
});
</script>

<template>
  <nav class="navbar">
    <div class="container">
      <div class="nav-content">
        <div class="nav-left">
          <a class="logo" href="#">
            <img class="logo-img" :src="logoImg" alt="Vue-Recept" />
          </a>
        </div>

        <button class="hamburger" @click="toggleMenu" aria-label="Toggle menu">
          <span class="hamburger-line"></span>
          <span class="hamburger-line"></span>
          <span class="hamburger-line"></span>
        </button>

        <div :class="['nav-links', { 'open': isMenuOpen }]">
          <router-link to="/" class="nav-link" @click="closeMenu">Home</router-link>
          <router-link to="/favorites" class="nav-link" @click="closeMenu">
            Favorites
          </router-link>
          <template v-if="!isLoggedIn">
            <router-link to="/login" class="nav-link" @click="closeMenu">
              Sign In
            </router-link>
            <router-link to="/signup" class="nav-link" @click="closeMenu">
              Sign Up
            </router-link>
          </template>
          <button v-else @click="logout" class="nav-link">
            Logout
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped>

</style>
 -->


 <!-- src/components/ResponsiveNavbar.vue -->
<script setup lang="ts">
import { ref, watch, onMounted } from 'vue';
import { useRoute, useRouter } from 'vue-router';
import logoImg from '@/assets/img/logo.png';

const route = useRoute();
const router = useRouter();
const isMenuOpen = ref(false);

// Reaktiv variabel för inloggningsstatus
const isLoggedIn = ref(!!localStorage.getItem('authToken'));

function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value;
}

function closeMenu() {
  isMenuOpen.value = false;
}

function logout() {
  localStorage.removeItem('authToken');
  isLoggedIn.value = false;
  router.push('/');
  closeMenu();
}

// Uppdatera inloggningsstatus när komponenten laddas
onMounted(() => {
  isLoggedIn.value = !!localStorage.getItem('authToken');
});

// Blockera scroll när menyn är öppen
watch(isMenuOpen, (val) => {
  document.body.style.overflow = val ? 'hidden' : '';
});

// Stäng menyn när vi navigerar till en annan sida
watch(() => route.path, () => {
  closeMenu();
});
</script>

<template>
  <nav class="navbar">
    <div class="container">
      <div class="nav-content">
        <!-- Logo -->
        <div class="nav-left">
          <router-link to="/" class="logo">
            <img class="logo-img" :src="logoImg" alt="Vue-Recept" />
            <span class="logo-text">Recept</span>
          </router-link>
        </div>

        <!-- Hamburger -->
        <button class="hamburger" @click="toggleMenu" aria-label="Toggle menu">
          <span class="hamburger-line"></span>
          <span class="hamburger-line"></span>
          <span class="hamburger-line"></span>
        </button>

        <!-- Links -->
        <div :class="['nav-links', { open: isMenuOpen }]">
          <router-link to="/" class="nav-link">Home</router-link>
          <router-link to="/favorites" class="nav-link">Favorites</router-link>

          <template v-if="!isLoggedIn">
            <router-link to="/login" class="nav-link">Sign In</router-link>
            <router-link to="/signup" class="nav-link">Sign Up</router-link>
          </template>

          <button v-else @click="logout" class="nav-link">Logout</button>
        </div>
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  overflow-x: hidden;
}

.navbar {
  border-bottom: 1px solid #ff8c00;
  background: #fff;
  position: sticky;
  top: 0;
  z-index: 1000;
}

.container {
  max-width: 1120px;
  margin: 0 auto;
  padding: 0 16px;
}

.nav-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 70px;
}

.logo {
  display: flex;
  align-items: center;
  text-decoration: none;
}

.logo-img {
  height: 50px;
  width: auto;
  border-radius: 50%;
}

.logo-text {
  color: #ff8c00;
  font-size: 1.25rem;
  font-weight: bold;
  margin-left: 8px;
}

/* Hamburger */
.hamburger {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 28px;
  height: 22px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
  z-index: 1100;
}

.hamburger-line {
  width: 100%;
  height: 3px;
  background: #ff8c00;
  border-radius: 2px;
  transition: all 0.3s ease;
}

/* Links */
.nav-links {
  display: flex;
  gap: 16px;
  align-items: center;
}

.nav-link {
  color: #ff8c00;
  padding: 10px 14px;
  text-decoration: none;
  font-weight: bold;
  border-radius: 8px;
  transition: background 0.3s ease;
  cursor: pointer;
  background: transparent;
  border: none;
}

.nav-link:hover {
  background: rgba(255, 140, 0, 0.1);
}

.nav-link.router-link-active,
.nav-link.router-link-exact-active {
  background: rgba(255, 140, 0, 0.2);
}

/* 🔹 Mobil */
@media (max-width: 768px) {
  .hamburger {
    display: flex;
  }

  .nav-links {
    position: fixed;
    top: 0;
    right: -100%;
    width: 70%;
    max-width: 280px;
    height: 100vh;
    background: #fff;
    flex-direction: column;
    align-items: flex-start;
    padding: 100px 20px 20px;
    gap: 12px;
    box-shadow: -2px 0 6px rgba(0, 0, 0, 0.15);
    transition: right 0.3s ease-in-out;
    z-index: 1000;
  }

  .nav-links.open {
    right: 0;
  }

  .nav-link {
    width: 100%;
    text-align: left;
    font-size: 1rem;
    padding: 12px;
  }
}
</style>
