<template>
  <div class="max-w-7xl mx-auto flex flex-col relative">

    <!-- Navbar -->
    <nav 
      :class="[
        'fixed top-0 left-0 right-0 z-50 transition-all duration-300',
        isScrolled 
          ? 'backdrop-blur-md bg-[#101010] bg-opacity-95 border-b border-[#2a2a2a] shadow-lg' 
          : 'backdrop-blur-sm bg-[#101010] bg-opacity-80'
      ]"
    >
      <div class="max-w-7xl mx-auto flex items-center justify-between px-5 py-4">
        <button @click="redirectToHome" class="flex items-center">
          <span class="text-xl font-bold text-red-500 tracking-tight hover:text-white transition">
            Eng.Abdelrhman(D3ff4ult);
          </span>
        </button>

        <!-- Desktop Menu -->
        <div class="hidden md:flex space-x-6 text-sm font-medium">
          <router-link to="/" class="text-gray-300 hover:text-white transition">Home</router-link>
          <router-link to="/about" class="text-gray-300 hover:text-white transition">About</router-link>
          <router-link to="/portfolio" class="text-gray-300 hover:text-white transition">Projects</router-link>
          <router-link to="/contact" class="text-gray-300 hover:text-white transition">Contact</router-link>
        </div>

        <!-- Mobile Menu Button -->
        <button class="md:hidden text-red-500" @click="toggleMobileMenu">
          <i class="fas fa-bars text-xl"></i>
        </button>
      </div>

      <!-- Mobile Menu Items -->
      <div v-if="mobileMenuOpen" class="md:hidden px-5 pb-4 space-y-2">
        <router-link @click="closeMobileMenu" to="/" class="block text-gray-300 hover:text-white">Home</router-link>
        <router-link @click="closeMobileMenu" to="/about" class="block text-gray-300 hover:text-white">About</router-link>
        <router-link @click="closeMobileMenu" to="/portfolio" class="block text-gray-300 hover:text-white">Projects</router-link>
        <router-link @click="closeMobileMenu" to="/contact" class="block text-gray-300 hover:text-white">Contact</router-link>
      </div>
    </nav>

    <!-- Main Content -->
    <div class="pt-[100px]">
      <router-view />
    </div>

    <!-- Footer -->
    <footer class="bg-[#0f0f0f] border-t border-[#2c2c2c] text-gray-300 py-10 px-6">
      <div class="container mx-auto grid grid-cols-1 md:grid-cols-3 gap-8 text-sm">
        <div>
          <h2 class="text-lg font-semibold text-red-500 mb-3">Information</h2>
          <p>Back-end developer crafting modern sites</p>
        </div>

        <div>
          <h3 class="text-red-400 font-semibold mb-2">Quick Links</h3>
          <ul class="space-y-1">
            <li><router-link to="/" class="hover:text-white transition">Home</router-link></li>
            <li><router-link to="/about" class="hover:text-white transition">About</router-link></li>
            <li><router-link to="/portfolio" class="hover:text-white transition">Projects</router-link></li>
            <li><router-link to="/contact" class="hover:text-white transition">Contact</router-link></li>
          </ul>
        </div>

        <div>
          <h3 class="text-red-400 font-semibold mb-2">Contact Info</h3>
          <ul class="space-y-1">
            <li>Email: <a href="mailto:abdoh6112113@gmail.com" class="hover:text-white transition">abdoh6112113@gmail.com</a></li>
            <li>Phone: <a href="tel:+201149969986" class="hover:text-white transition">+20 114 996 9986</a></li>
            <li>Location: Giza, Egypt</li>
          </ul>
        </div>
      </div>
      <div class="flex justify-center gap-4 mt-8">
        <a href="https://github.com/d3ff4ult" target="_blank" class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-800 text-red-500 hover:text-white transition">
          <i class="fab fa-github"></i>
        </a>
      </div>

      <div class="mt-6 text-center text-gray-500 text-xs">
        © {{ new Date().getFullYear() }} D3ff4ult. All rights reserved.
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isScrolled: false,
      mobileMenuOpen: false
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    redirectToHome() {
      this.$router.push("/");
    },
    handleScroll() {
      this.isScrolled = window.scrollY > 30;
    },
    toggleMobileMenu() {
      this.mobileMenuOpen = !this.mobileMenuOpen;
    },
    closeMobileMenu() {
      this.mobileMenuOpen = false;
    }
  }
};
</script>

<style>
/* Your same styles */
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

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
  font-size: 15px;
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
  margin-top: 0.08em;
  width: 100%;
  height: 4px;
  margin-top: 0.08em;
  border-radius: 2px;
  background-color: #ff03038a;
}

nav a.router-link-exact-active:hover {
  color: #ffffff;
}

h1, h2, h3 {
  font-family: 'Poppins', sans-serif;
  font-weight: 600;
  color: #ffffff;
}

p {
  font-size: 14px;
  color: #bcbcbc;
}

@keyframes fadeInLeft {
  0% {
    opacity: 0;
    transform: translateX(-100%);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}
</style>
