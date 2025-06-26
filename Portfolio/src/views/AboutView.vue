<script>
export default {
  data() {
    return {
      activeTab: 1,
      d3ff4ult: [
        {
          id: 1,
          name: 'HTML',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/1051/1051277.png',
          status: 'Intermediate'
        },
        {
          id: 2,
          name: 'CSS',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/732/732190.png',
          status: 'Beginner'
        },
        {
          id: 3,
          name: 'PHP',
          imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-php-2038871-1720084.png',
          status: 'Intermediate'
        },
        {
          id: 4,
          name: 'Laravel',
          imageUrl: 'https://cdn.worldvectorlogo.com/logos/laravel-2.svg',
          status: 'Intermediate'
        },
      ],
      tools: [
        {
          id: 1,
          name: 'Git',
          imageUrl: 'https://git-scm.com/images/logos/downloads/Git-Icon-1788C.png',
          status: 'Version Control'
        },
        {
          id: 2,
          name: 'GitHub',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/25/25231.png',
          status: 'Git Hosting'
        },
        {
          id: 3,
          name: 'NPM',
          imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-npm-3-1175132.png',
          status: 'Package Manager'
        },
        {
          id: 4,
          name: 'MySQL',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/5968/5968313.png',
          status: 'Database'
        },
      ]
    };
  }
}
</script>

<template>
<div
  class="bg-[#1e1e1f] px-5 py-5 md:px-12 md:py-10 text-left border border-[#383838] rounded-3xl text-amber-50 mx-3 mb-5">
  <article data-page="about">
    <header>
<div class="text-[rgba(255,3,3,0.54)] text-2xl font-bold mb-5 fadein-bot title-section flex items-center">
  About Me &nbsp;
  <div class="h-[1px] w-32 bg-[#444] md:w-96 aos-init aos-animate" data-aos="zoom-in-left" data-aos-duration="600"></div>
</div>
    </header>

    <section
      class="text-sm md:text-lg text-justify flex flex-col gap-4 md:flex-row md:gap-8 md:justify-left md:items-center">
      <div class="flex justify-center md:justify-start fadein-right">
<img 
  src="/img/me.jpg" 
  alt="My Avatar"
  class="w-32 h-32 sm:w-40 sm:h-40 md:w-48 md:h-48 lg:w-56 lg:h-56 object-cover rounded-full border-4 border-[rgba(255,3,3,0.54)] shadow-lg transition-all duration-300 hover:scale-105"
/>

      </div>

      <div class="md:w-7/12">
        <p class="mb-3 md:mb-7 fadein-left fadeins-1">
          &nbsp; &nbsp; &nbsp; Hi everyone! My name is Abdelrhman Hesham. I'm a student at Menofia University (MU),
          studying in the Faculty of Computer and Information, Computer Science Department.
        </p>

        <p class="mb-3 fadein-left fadeins-2">
          &nbsp; &nbsp; &nbsp; My job is to build your project to be functional and user-friendly yet still attractive.
          In addition, I provide a personal touch to your project and ensure that the project catches attention and is
          easy to use.
          My goal is to convey your message and identity in the most creative way.
          You can contact me through my social media accounts.
        </p>
      </div>
    </section>
  </article>
</div>


 <div class="px-5 py-5 md:px-12 md:py-10 text-left text-amber-50 mx-3">
  <article data-page="about">
    <header>
      <div class="text-[rgba(255,3,3,0.54)] text-2xl font-bold mb-5 fadein-bot title-section flex items-center">
        Skills &nbsp;
        <div class="h-[1px] w-10 bg-[#444] md:w-20 aos-init aos-animate" data-aos="zoom-in-left"
          data-aos-duration="600"></div>
      </div>
    </header>

    <section>
      <div>
        <ul class="flex flex-wrap text-sm font-medium text-center text-gray-500 dark:text-gray-400 mb-5">
          <li class="mr-2">
            <button
              class="inline-block px-4 py-3 rounded-lg hover:text-[rgba(255,3,3,0.54)] hover:bg-black transition duration-300"
              :class="{ 'text-[rgba(255,3,3,0.54)] bg-black': activeTab === 1 }"
              @click="activeTab = 1">
              Skills
            </button>
          </li>
          <li class="mr-2">
            <button
              class="inline-block px-4 py-3 rounded-lg hover:text-[rgba(255,3,3,0.54)] hover:bg-black transition duration-300"
              :class="{ 'text-[rgba(255,3,3,0.54)] bg-black': activeTab === 2 }"
              @click="activeTab = 2">
              Tools
            </button>
          </li>
        </ul>
      </div>

      <div v-show="activeTab === 1">
        <div class="grid grid-cols-2 gap-4 pb-32 md:grid-cols-3 md:gap-8 xl:grid-cols-4 xl:gap-10 2xl:gap-12">
          <div v-for="item in d3ff4ult" :key="item.id">
            <div
              class="item-d3ff4ult flex cursor-pointer items-center gap-2 rounded border border-[rgba(255,3,3,0.54)] px-2 py-2 hover:bg-black hover:bg-opacity-40 md:gap-3 lg:px-3 transition duration-300">
              <div class="flex h-12 w-12 items-center justify-center p-0 lg:h-16 lg:w-16 lg:p-2 zoom-in">
                <img alt="Skill" loading="lazy" width="32" height="32" decoding="async" data-nimg="1"
                  class="img-d3ff4ult drop-shadow-xl transition-all duration-300 h-[65%] w-[65%] lg:h-[85%] lg:w-[85%]"
                  :src="item.imageUrl" style="color: transparent;">
              </div>
              <div class="flex items-center text-sm md:text-base lg:text-lg">
                <div class="d3ff4ult-label font-medium text-secondary transition-all duration-300 translate-y-0">
                  {{ item.name }}
                </div>
                <div
                  class="status-d3ff4ult opacity-0 absolute mt-5 text-[10px] text-[rgba(255,3,3,0.54)] transition-all duration-300 md:text-xs lg:text-sm">
                  {{ item.status }}
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div v-show="activeTab === 2">
        <div class="grid grid-cols-2 gap-4 pb-32 md:grid-cols-3 md:gap-8 xl:grid-cols-4 xl:gap-10 2xl:gap-12">
          <div v-for="item in tools" :key="item.id">
            <div
              class="item-d3ff4ult flex cursor-pointer items-center gap-2 rounded border border-[rgba(255,3,3,0.54)] px-2 py-2 hover:bg-black hover:bg-opacity-40 md:gap-3 lg:px-3 transition duration-300">
              <div class="flex h-12 w-12 items-center justify-center p-0 lg:h-16 lg:w-16 lg:p-2 zoom-in">
                <img alt="Tool" loading="lazy" width="32" height="32" decoding="async" data-nimg="1"
                  class="img-d3ff4ult drop-shadow-xl transition-all duration-300 h-[65%] w-[65%] lg:h-[85%] lg:w-[85%]"
                  :src="item.imageUrl" style="color: transparent;">
              </div>
              <div class="flex items-center text-sm md:text-base lg:text-lg">
                <div class="d3ff4ult-label font-medium text-secondary transition-all duration-300 translate-y-0">
                  {{ item.name }}
                </div>
                <div
                  class="status-d3ff4ult opacity-0 absolute mt-5 text-[10px] text-[rgba(255,3,3,0.54)] transition-all duration-300 md:text-xs lg:text-sm">
                  {{ item.status }}
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

<style>
.fadein-left {
  opacity: 0;
  animation: fadeInLeft 0.5s ease-out forwards;
}

@keyframes fadeInLeft {
  0% {
    opacity: 0;
    transform: translateX(100%);
  }

  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

.fadeins-1 {
  animation-delay: 500ms;
}

.fadeins-2 {
  animation-delay: 800ms;
}

.img-d3ff4ult,
.d3ff4ult-label {
  transition: transform 0.3s ease;
}

.item-d3ff4ult:hover .img-d3ff4ult {
  transform: scale(1.3);
}

.item-d3ff4ult:hover .d3ff4ult-label {
  transform: translateY(-12px);
}

.item-d3ff4ult:hover .status-d3ff4ult {
  opacity: 1;
}
</style>
