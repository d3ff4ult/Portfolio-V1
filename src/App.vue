<template>
  <nav 
    :class="[
      'fixed top-0 left-0 right-0 z-50 transition-all duration-300',
      isScrolled 
        ? 'backdrop-blur-md bg-[#101010] bg-opacity-95 border-b border-[#2a2a2a] shadow-lg' 
        : 'backdrop-blur-sm bg-[#101010] bg-opacity-80'
    ]"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <!-- Logo -->
        <button @click="navigateTo('/')" class="flex items-center group">
          <span class="text-xl font-bold text-red-500 tracking-tight group-hover:text-white transition-colors duration-300">
            Eng.Abdelrhman(D3ff4ult);
          </span>
        </button>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center space-x-8">
          <router-link
            v-for="item in navItems"
            :key="item.path"
            :to="item.path"
            class="text-gray-300 hover:text-white transition-colors duration-300 text-sm font-medium relative group"
            active-class="router-link-exact-active"
          >
            {{ item.label }}
            <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-red-500 transition-all duration-300 group-hover:w-full"></span>
          </router-link>
        </div>

        <!-- Mobile Menu Button -->
        <button
          @click="toggleMobileMenu"
          class="md:hidden p-2 rounded-lg text-gray-300 hover:text-white hover:bg-gray-800 transition-colors duration-300"
          aria-label="Toggle mobile menu"
        >
          <svg v-if="isMobileMenuOpen" class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
          </svg>
          <svg v-else class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile Menu -->
    <div 
      :class="[
        'md:hidden transition-all duration-300 ease-in-out',
        isMobileMenuOpen ? 'max-h-64 opacity-100' : 'max-h-0 opacity-0 overflow-hidden'
      ]"
    >
      <div class="px-4 pt-2 pb-4 space-y-2 bg-[#101010] bg-opacity-95 border-t border-[#2a2a2a]">
        <router-link
          v-for="(item, index) in navItems"
          :key="item.path"
          :to="item.path"
          @click="closeMobileMenu"
          class="block w-full text-left px-4 py-3 text-gray-300 hover:text-white hover:bg-gray-800 rounded-lg transition-all duration-300"
          :style="{ transitionDelay: isMobileMenuOpen ? `${index * 50}ms` : '0ms' }"
        >
          {{ item.label }}
        </router-link>
      </div>
    </div>

    <!-- Mobile Menu Overlay -->
    <div
      v-if="isMobileMenuOpen"
      @click="closeMobileMenu"
      class="fixed inset-0 z-40 bg-black bg-opacity-50 md:hidden"
    />
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { useRouter } from 'vue-router'

const router = useRouter()
const isMobileMenuOpen = ref(false)
const isScrolled = ref(false)

const navItems = [
  { label: 'Home', path: '/' },
  { label: 'About', path: '/about' },
  { label: 'Projects', path: '/portfolio' },
  { label: 'Contact', path: '/contact' }
]

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false
}

const navigateTo = (path) => {
  closeMobileMenu()
  router.push(path)
}

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style>
::-webkit-scrollbar {
  width: 5px;
  height: 5px;
}

::-webkit-scrollbar-track {
  background: transparent;
  border-radius: 5px;
}

::-webkit-scrollbar-thumb {
  background: #ffffff;
  border-radius: 5px;
}

::-webkit-scrollbar-button {
  width: 20px;
}

body {
  font-family: 'Poppins', sans-serif;
  background-color: #0b0b0b;
  color: #d1d1d1;
  font-size: 16px;
  line-height: 1.6;
  padding: 0;
  margin: 0;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  transition: color 0.3s;
}

nav a.router-link-exact-active {
  display: inline-flex;
  flex-direction: column;
  color: #ff03038a;
  transition: color 0.3s;
}

nav a.router-link-exact-active::after {
  display: inline-block;
  content: "";
  display: block;
  width: 100%;
  height: 4px;
  margin-top: 0.08em;
  border-radius: 2px;
  background-color: #ff03038a;
}

nav a.router-link-exact-active:hover {
  color: #ffffff;
}
</style>
