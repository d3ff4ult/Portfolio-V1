<template>
  <div class="px-5 py-5 md:px-12 md:py-10 text-left mx-3">
    <article data-page="about">
      <header>
        <div
          class="text-2xl font-bold text-[#ff0303] mb-10 fadein-bot title-section flex items-center justify-center flex-col">
          <h4>Past Project Experience</h4>
          <h4 class="text-base font-normal text-white">
            Explore the projects I've worked on so far
          </h4>
        </div>
      </header>
      <section>
        <div>
          <div
            class="grid grid-cols-1 gap-4 pb-32 md:grid-cols-3 md:gap-3 xl:grid-cols-3 xl:gap-3 2xl:gap-5 fade-zoom-in">
            <div v-for="item in items" :key="item.id">
              <div
                class="item-card flex flex-col items-center gap-2 rounded bg-white hover:bg-gray-100 border border-[#ccc] rounded-xl text-[#2e2e2e] md:gap-3 px-5 py-5 lg:px-5 transition-all duration-300">
                <div class="w-full h-auto">
                  <img :src="item.imageUrl" alt="Project Image" loading="lazy"
                    class="drop-shadow-xl rounded-xl w-full" />
                </div>
                <div class="w-full flex flex-col gap-2 items-center text-sm md:text-base lg:text-lg mt-3">
                  <div class="font-semibold text-[#ff0303]">
                    {{ item.name }}
                  </div>
                  <div class="w-full text-left text-sm text-[#2e2e2e]">
                    {{ item.status }}
                  </div>
                  <div class="w-full mt-2 text-left text-xs text-[#ff0303]">
                    {{ item.d3ff4ult }}
                  </div>
                  <div class="w-full flex justify-end gap-3 mt-2">
                    <a v-if="item.github !== 'null'" :href="item.github" target="_blank" rel="noreferrer"
                      title="View GitHub repository" class="hover:text-[#ff0303]">
                      <svg xmlns="http://www.w3.org/2000/svg" stroke="currentColor" fill="none" stroke-width="2"
                        viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" height="18" width="18"
                        class="transition-colors duration-300 hover:stroke-[#ff0303]">
                        <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61
                          c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77
                          A5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38
                          13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07
                          0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42
                          3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path>
                      </svg>
                    </a>
                    <a v-if="item.demo !== 'null'" :href="item.demo" target="_blank" rel="noreferrer"
                      title="View finished project" class="hover:text-[#ff0303]">
                      <svg xmlns="http://www.w3.org/2000/svg" stroke="currentColor" fill="none" stroke-width="2"
                        viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" height="18" width="18"
                        class="transition-colors duration-300 hover:stroke-[#ff0303]">
                        <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6" />
                        <polyline points="15 3 21 3 21 9" />
                        <line x1="10" y1="14" x2="21" y2="3" />
                      </svg>
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </article>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeTab: 1,
      items: [
        {
          id: 1,
          name: 'Personal Website',
          imageUrl: '/img/mysite.jpg',
          status: 'My personal website where I display my profile, skills, and projects. Also used to test new ideas.',
          d3ff4ult: 'VueJS 3, Tailwind CSS',
          github: 'https://github.com/d3ff4ult/Portfolio-V1',
          demo: 'https://portfolio-v1-cj9u.vercel.app/',
        },
      ],
    };
  },
};
</script>

<style scoped>
.item-card:hover {
  transform: translateY(-6px);
}

.fade-zoom-in {
  animation: fadeZoomIn 1s ease-in-out;
}

@keyframes fadeZoomIn {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }

  100% {
    opacity: 1;
    transform: scale(1);
  }
}
</style>
