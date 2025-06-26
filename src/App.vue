<template>
  <div class="max-w-7xl mx-auto flex flex-col relative">

    <nav class="fixed top-0 left-0 w-full z-50 backdrop-blur-md bg-[#121212]/80 border-b border-gray-700">
  <div class="max-w-7xl mx-auto px-4 py-3 flex items-center justify-between">
    <!-- Logo -->
    <button @click="redirectToHome" class="flex items-center">
      <span class="text-lg text-[#ff03038a] font-semibold whitespace-nowrap hover:text-amber-100">
        Eng.Abdelrhman(D3ff4ult);
      </span>
    </button>

   
    <button @click="toggleMobileMenu"
      class="md:hidden text-gray-200 focus:outline-none text-2xl p-2 transition hover:text-white z-50">
      ☰
    </button>
  </div>

  
  <div :class="['px-4 pb-4 md:pb-0 md:flex md:items-center md:justify-center md:space-x-8', isMobileMenuOpen ? 'block' : 'hidden']">
    <ul class="flex flex-col md:flex-row md:space-x-8 md:text-sm md:font-medium">
      <li>
        <router-link @click="toggleMobileMenu" to="/" class="text-gray-300 hover:text-white block py-2 px-4">
          Home
        </router-link>
      </li>
      <li>
        <router-link @click="toggleMobileMenu" to="/about" class="text-gray-300 hover:text-white block py-2 px-4">
          About
        </router-link>
      </li>
      <li>
        <router-link @click="toggleMobileMenu" to="/portfolio" class="text-gray-300 hover:text-white block py-2 px-4">
          Portfolio
        </router-link>
      </li>
      <li>
        <router-link @click="toggleMobileMenu" to="/contact" class="text-gray-300 hover:text-white block py-2 px-4">
          ContactMe
        </router-link>
      </li>
    </ul>
  </div>
</nav>


    
    <div class="md:mt-[100px]">
      <router-view />
    </div>

    
    <footer class="bg-[#121212] border-t border-[#383838] text-white py-10 px-5">
      <div class="container mx-auto grid grid-cols-1 md:grid-cols-3 gap-8">
        <div>
          <h2 class="text-xl font-bold text-[#ff0303] mb-4">Information</h2>
          <p class="text-gray-400">Back-end developer crafting modern sites</p>
        </div>

        <div>
          <h3 class="text-red-600 font-semibold mb-3">Quick Links</h3>
          <ul class="space-y-2 text-gray-400">
            <li><router-link to="/" class="hover:text-white">Home</router-link></li>
            <li><router-link to="/about" class="hover:text-white">About</router-link></li>
            <li><router-link to="/portfolio" class="hover:text-white">Portfolio</router-link></li>
            <li><router-link to="/contact" class="hover:text-white">ContactMe</router-link></li>
          </ul>
        </div>

        <div>
          <h3 class="text-red-600 font-semibold mb-3">Contact Info</h3>
          <ul class="space-y-2 text-gray-400">
            <li>Email: <a href="mailto:abdoh6112113@gmail.com" class="hover:text-white">abdoh6112113@gmail.com</a></li>
            <li>Phone: <a href="tel:+201149969986" class="hover:text-white">+20 114 996 9986</a></li>
            <li>Location: Giza, Giza, Egypt</li>
          </ul>
        </div>
      </div>
      <!-- Social Icons in Footer -->
      <div class="flex justify-center gap-4 mt-8">
        <a href="https://www.linkedin.com/in/abdelrhman-hesham-395268335" target="_blank"
          class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-800 text-red-500 hover:bg-gray-700 transition"
          aria-label="LinkedIn">
          <i class="fab fa-linkedin-in"></i>
        </a>
        <a href="https://snapchat.com/t/Hk3jmyAg" target="_blank"
          class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-800 text-red-500 hover:bg-gray-700 transition"
          aria-label="Snapchat">
          <i class="fab fa-snapchat-ghost"></i>
        </a>
        <a href="https://www.facebook.com/abdo.hesham.52438" target="_blank"
          class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-800 text-red-500 hover:bg-gray-700 transition"
          aria-label="Facebook">
          <i class="fab fa-facebook-f"></i>
        </a>
        <a href="https://www.instagram.com/abdo.h.28" target="_blank"
          class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-800 text-red-500 hover:bg-gray-700 transition"
          aria-label="Instagram">
          <i class="fab fa-instagram"></i>
        </a>
        <a href="https://github.com/d3ff4ult" target="_blank"
          class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-800 text-red-500 hover:bg-gray-700 transition"
          aria-label="GitHub">
          <i class="fab fa-github"></i>
        </a>
      </div>

      <div class="mt-8 text-center text-gray-500 text-sm">
        © {{ new Date().getFullYear() }} D3ff4ult. All rights reserved.
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  methods: {
    redirectToHome() {
      this.$router.push('/');
    },
    toggleMobileMenu() {
      this.isMobileMenuOpen = !this.isMobileMenuOpen;
    }
  }
}
</script>

<style>
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
  background: hsla(0, 0%, 100%, 0);
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
  background: hsl(0, 0%, 7%);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
}

nav {
  padding: 30px;
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
  margin-top: 0.08em;
  width: 100%;
  height: 4px;
  border-radius: 2px;
  background-color: #ff03038a;
}

nav a.router-link-exact-active:hover {
  color: hsl(0, 0%, 100%);
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
