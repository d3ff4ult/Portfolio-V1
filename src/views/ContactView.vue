<template>
  <section id="Contact" class="py-20 bg-[#121212]">
    <div class="container mx-auto px-4 md:px-6">
      <div class="text-center mb-16">
        <h2 class="text-3xl md:text-4xl font-bold mb-4 text-red-500">
          Let's Build Something<br />
          <span class="text-red-500">Incredible Together</span>
        </h2>
        <p class="text-gray-500 max-w-2xl mx-auto">
          Got an idea or want to collaborate on something awesome? I'm just a message away. Drop your details below, and
          let's connect.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
        <!-- Contact Information -->
        <div>
          <h3 class="text-xl font-semibold mb-6 text-red-500">Contact Information</h3>
          <div class="space-y-6 text-gray-500">
            <div class="flex items-start gap-4">
              <div class="p-3 bg-gray-800 rounded-lg text-red-500">
                <Mail :size="20" />
              </div>
              <div>
                <h4 class="font-medium mb-1 text-red-500">Email</h4>
                <a href="mailto:abdoh6112113@gmail.com" class="hover:text-white transition-colors">
                  abdoh6112113@gmail.com
                </a>
              </div>
            </div>

            <div class="flex items-start gap-4">
              <div class="p-3 bg-gray-800 rounded-lg text-red-500">
                <Phone :size="20" />
              </div>
              <div>
                <h4 class="font-medium mb-1 text-red-500">Phone</h4>
                <a href="tel:+201149969986" class="hover:text-white transition-colors">
                  +20 114 996 9986
                </a>
              </div>
            </div>

            <div class="flex items-start gap-4">
              <div class="p-3 bg-gray-800 rounded-lg text-red-500">
                <MapPin :size="20" />
              </div>
              <div>
                <h4 class="font-medium mb-1 text-red-500">Location</h4>
                <p>Giza, Giza, Egypt</p>
              </div>
            </div>
          </div>


          <div class="mt-10">
            <h3 class="text-xl font-semibold mb-4 text-red-500">Follow Me</h3>
            <div class="flex gap-4">
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
            </div>
          </div>


        </div>

       
        <div>
          <form @submit.prevent="handleSubmit" class="space-y-6">
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
              <div>
                <label for="name" class="block text-sm font-medium mb-2 text-red-500">Your Name</label>
                <input type="text" id="name" name="name" required
                  class="w-full px-4 py-3 bg-white border border-gray-700 rounded-lg focus:outline-none focus:ring-2 focus:ring-red-500 focus:border-transparent transition-all"
                  placeholder="Name" />
              </div>
              <div>
                <label for="email" class="block text-sm font-medium mb-2 text-red-500">Your Email</label>
                <input type="email" id="email" name="email" required
                  class="w-full px-4 py-3 bg-white border border-gray-700 rounded-lg focus:outline-none focus:ring-2 focus:ring-red-500 focus:border-transparent transition-all"
                  placeholder="Email" />
              </div>
            </div>

            <div>
              <label for="subject" class="block text-sm font-medium mb-2 text-red-500">Subject</label>
              <input type="text" id="subject" name="subject" required
                class="w-full px-4 py-3 bg-white border border-gray-700 rounded-lg focus:outline-none focus:ring-2 focus:ring-red-500 focus:border-transparent transition-all"
                placeholder="Project Inquiry" />
            </div>

            <div>
              <label for="message" class="block text-sm font-medium mb-2 text-red-500">Message</label>
              <textarea id="message" name="message" required rows="5"
                class="w-full px-4 py-3 bg-white border border-gray-700 rounded-lg focus:outline-none focus:ring-2 focus:ring-red-500 focus:border-transparent transition-all"
                placeholder="Hello, I'd like to talk about..."></textarea>
            </div>

            <button type="submit"
              class="w-full px-6 py-3 rounded-lg bg-red-600 hover:bg-red-700 text-white font-medium shadow-lg hover:shadow-red-500/30 transition-all flex items-center justify-center gap-2">
              Send Message
              <Send :size="16" />
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Send, Mail, Phone, MapPin } from 'lucide-vue-next'
import { useRouter } from 'vue-router'

const router = useRouter()

function handleSubmit() {
  alert('Message sent successfully!')
  router.push('/')
}
</script>
