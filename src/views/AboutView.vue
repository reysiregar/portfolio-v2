<script>
export default {
  data() {
    return {
      activeTab: 1,
      tech: [
        {
          id: 1,
          name: 'HTML',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/1051/1051277.png',
          status: 'Beginner'
        },
        {
          id: 2,
          name: 'CSS',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/732/732190.png',
          status: 'Beginner'
        },
        {
          id: 3,
          name: 'Javascript',
          imageUrl: 'https://cdn.jsdelivr.net/npm/programming-languages-logos@0.0.3/src/javascript/javascript.svg',
          status: 'Beginner'
        },
        {
          id: 4,
          name: 'VueJS',
          imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-vue-282497.png?f=webp',
          status: 'Beginner'
        },
        {
          id: 5,
          name: 'NodeJS',
          imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-node-js-1174925.png',
          status: 'Beginner'
        },
        {
          id: 6,
          name: 'Tailwind',
          imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/d/d5/Tailwind_CSS_Logo.svg',
          status: 'Beginner'
        },
        {
          id: 7,
          name: 'ReactJS',
          imageUrl: 'https://cdn4.iconfinder.com/data/icons/logos-3/600/React.js_logo-512.png',
          status: 'Beginner'
        },
        {
          id: 9,
          name: 'WordPress',
          imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/9/98/WordPress_blue_logo.svg',
          status: 'Beginner'
        }
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
          imageUrl: 'https://icon-library.com/images/github-icon-white/github-icon-white-6.jpg',
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
          name: 'Vercel',
          imageUrl: 'https://vercel.com/favicon.ico',
          status: 'Deployment'
        },
        {
          id: 5,
          name: 'Xampp',
          imageUrl: 'https://www.apachefriends.org/images/xampp-logo-ac950edf.svg',
          status: 'Local Server'
        },
        {
          id: 6,
          name: 'Postman',
          imageUrl: '/img/postman-icon.svg',
          status: 'API Testing'
        },
        {
          id: 7,
          name: 'Canva',
          imageUrl: '/img/canva-icon.svg',
          status: 'Advanced'
        }
      ],
      timeline: [
        {
          id: 1,
          type: 'education',
          institution: 'SMA Negeri 9 Kota Bekasi',
          period: 'July 2020 - Graduated 2023'
        },
        {
          id: 2,
          type: 'education',
          institution: 'Gunadarma University',
          period: 'September 2023 - Present'
        },
        {
          id: 3,
          type: 'career',
          description: "Unemployed, actively seeking opportunities in web development."
        }
      ]
    };
  }
}
</script>
<template>
  <div
    class="bg-[#1e1e1f] px-5 py-5 md:px-12 md:py-10 text-left border border-[#383838] rounded-3xl text-blue-50 mx-3 mb-5">
    <article data-page="about">
      <header>
        <div class="text-2xl font-bold text-white mb-5 fadein-bot title-section flex items-center">
          About Me &nbsp;
          <div class="h-[1px] w-32 bg-blue-200 md:w-96 aos-init aos-animate" data-aos="zoom-in-left"
            data-aos-duration="600"></div>
        </div>
      </header>
      <section
        class="text-sm md:text-lg text-justify flex flex-col gap-4 md:flex-row md:gap-8 md:justify-left md:items-center">
        <div class="flex justify-center">
          <img class="w-9/12 rounded-full mb-3 fadein-up"
            src="/img/profile.jpg" alt="Profile picture of Reynaldi Siregar">
        </div>
        <div class="md:w-7/12">
          <p class="mb-3 md:mb-7 fadein-left fadeins-1">
            &nbsp; &nbsp; &nbsp; Hi everyone! My name is <strong>Reynaldi Siregar</strong>, a passionate <strong>Front-End Web Developer</strong> from Bekasi, Indonesia, with <strong>one year of experience</strong> in website development. I specialize in crafting <strong>responsive, user-friendly, and visually appealing</strong> websites that seamlessly blend functionality with aesthetics. Web development, to me, is more than just coding—it's a form of <strong>digital artistry</strong> that brings ideas to life through innovative and engaging designs.
          </p>
          <p class="mb-3 fadein-left fadeins-2">
            &nbsp; &nbsp; &nbsp; I take pride in writing clean, efficient code and staying up-to-date with the latest web technologies to ensure top-tier performance and user experience. My goal is to create websites that not only stand out but also provide effortless navigation and interaction. I'm excited to collaborate with businesses and individuals to transform their visions into high-quality digital experiences. Let's build something amazing together!
          </p>
        </div>
      </section>
    </article>
  </div>

  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-blue-50 mx-3">
    <article>
      <header>
        <div class="text-2xl font-bold text-white mb-10 fadein-bot title-section flex items-center">
          <div class="h-[1px] w-10 bg-blue-200 md:w-20 aos-init aos-animate" data-aos="zoom-in-left" data-aos-duration="600"></div>
          &nbsp; My Journey
        </div>
      </header>
      <section class="timeline-container-compact">
        <div v-for="item in timeline" :key="item.id" class="timeline-item-compact">
          <div class="timeline-icon-compact">
             <span v-if="item.type === 'education'">🎓</span>
             <span v-else>💼</span>
          </div>
          <div class="timeline-content-compact">
              <div v-if="item.type === 'education'" class="font-semibold text-blue-100">{{ item.institution }}</div>
              <div v-if="item.type === 'education'" class="text-xs text-blue-300">{{ item.period }}</div>
              <div v-if="item.type === 'career'" class="text-base text-blue-100">{{ item.description }}</div>
          </div>
        </div>
      </section>
    </article>
  </div>

  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-blue-50 mx-3">
    <article data-page="about">
      <header>
        <div class="text-2xl font-bold text-white mb-5 fadein-bot title-section flex items-center">
          <div class="h-[1px] w-10 bg-blue-200 md:w-20 aos-init aos-animate" data-aos="zoom-in-left"
            data-aos-duration="600"></div>
          &nbsp; Tech & Tools
        </div>
      </header>
      <section>
        <div>
          <ul class="flex flex-wrap text-sm font-medium text-center text-gray-500 dark:text-gray-400 mb-5">
            <li class="mr-2">
              <button class="inline-block px-4 py-3 rounded-lg hover:text-white"
                :class="{ 'text-blue-200 bg-blue-200 bg-opacity-10': activeTab === 1 }" @click="activeTab = 1">Tech Stack</button>
            </li>
            <li class="mr-2">
              <button class="inline-block px-4 py-3 rounded-lg hover:text-white"
                :class="{ 'text-blue-200 bg-blue-200 bg-opacity-10': activeTab === 2 }" @click="activeTab = 2">Tools</button>
            </li>
          </ul>
        </div>
        <div v-show="activeTab === 1">
          <div class="grid grid-cols-2 gap-4 pb-32 md:grid-cols-3 md:gap-8 xl:grid-cols-4 xl:gap-10 2xl:gap-12">
            <div v-for="item in tech" :key="item.id">
              <div
                class="item-tech flex cursor-pointer items-center gap-2 rounded border border-blue-200 px-2 py-2 hover:bg-blue-200 hover:bg-opacity-10 md:gap-3 lg:px-3">
                <div class="flex h-12 w-12 items-center justify-center p-0 lg:h-16 lg:w-16 lg:p-2 zoom-in">
                  <img alt="HTML" width="32" height="32" decoding="async" data-nimg="1"
                    class="img-tech drop-shadow-xl transition-all duration-300 h-[65%] w-[65%] lg:h-[85%] lg:w-[85%]  "
                    :src="item.imageUrl" style="color: transparent;">
                </div>
                <div class="flex items-center text-sm md:text-base lg:text-lg">
                  <div class="tech font-medium text-secondary transition-all duration-300 translate-y-0 ">{{ item.name }}
                  </div>
                  <div
                    class="status-tech opacity-0 absolute mt-5 text-[10px] text-blue-200 transition-all duration-300 md:text-xs lg:text-sm">
                    {{ item.status }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div v-show="activeTab === 2">
          <div class="grid grid-cols-2 gap-4 pb-32 md:grid-cols-3 md:gap-8 xl:grid-cols-4 xl:gap-10 2xl:gap-12">
            <div v-for="item in tools" :key="item.id">
              <div
                class="item-tech flex cursor-pointer items-center gap-2 rounded border border-blue-200 px-2 py-2 hover:bg-blue-200 hover:bg-opacity-10 md:gap-3 lg:px-3">
                <div class="flex h-12 w-12 items-center justify-center p-0 lg:h-16 lg:w-16 lg:p-2 zoom-in">
                  <img alt="HTML" width="32" height="32" decoding="async" data-nimg="1"
                    class="img-tech drop-shadow-xl transition-all duration-300 h-[65%] w-[65%] lg:h-[85%] lg:w-[85%]  "
                    :src="item.imageUrl" style="color: transparent;">
                </div>
                <div class="flex items-center text-sm md:text-base lg:text-lg">
                  <div class="tech font-medium text-secondary transition-all duration-300 translate-y-0 ">{{ item.name }}
                  </div>
                  <div
                    class="status-tech opacity-0 absolute mt-5 text-[10px] text-blue-200 transition-all duration-300 md:text-xs lg:text-sm">
                    {{ item.status }}</div>
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
  animation: fadeInSmooth 0.8s ease-out forwards;
}

@keyframes fadeInSmooth {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

.fadeins-1 {
  animation-delay: 500ms;
}

.fadeins-2 {
  animation-delay: 800ms;
}

/* Respect user's motion preferences */
@media (prefers-reduced-motion: reduce) {
  .fadein-left,
  .fadeins-1,
  .fadeins-2 {
    animation: none;
    opacity: 1 !important;
  }
}

.img-tech,
.tech {
  transition: transform 0.3s ease;
}

.item-tech:hover .img-tech {
  transform: scale(1.3);
}

.item-tech:hover .tech {
  transform: translateY(-12px);
}

.item-tech:hover .status-tech {
  opacity: 1;
}

.timeline {
  position: relative;
  margin-left: 1.5rem;
  padding-left: 1.5rem;
  border-left: 2px solid #a5b4fc;
}
.timeline-item {
  position: relative;
  margin-bottom: 1.5rem;
  padding-left: 0.5rem;
}
.timeline-dot {
  position: absolute;
  left: -1.1rem;
  top: 0.3rem;
  width: 0.8rem;
  height: 0.8rem;
  background: #a5b4fc;
  border-radius: 50%;
  border: 2px solid #fff;
  box-shadow: 0 0 0 2px #a5b4fc;
}
.timeline-content {
  margin-left: 0.5rem;
}
.timeline-cards {
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
  max-width: 700px;
  width: 100%;
}
.timeline-card {
  display: flex;
  align-items: center;
  background: transparent;
  border: 1px solid #bfdbfe; /* Tailwind's blue-200 */
  border-radius: 0.3rem;
  padding: 1rem 1.25rem;
  box-shadow: none;
  transition: box-shadow 0.2s;
}
.timeline-card:hover {
  box-shadow: none;
}
.timeline-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 2.5rem;
  height: 2.5rem;
  font-size: 1.5rem;
  border-radius: 50%;
  margin-right: 1rem;
  background: #bfdbfe;
  color: #232336;
  box-shadow: 0 0 0 2px #bfdbfe;
}
.timeline-card-content {
  flex: 1;
}

.timeline-container-compact {
  position: relative;
  max-width: 700px;
  margin: 0;
  padding-left: 60px; 
}

.timeline-container-compact::before {
  content: '';
  position: absolute;
  left: 20px;
  top: 0;
  bottom: 0;
  width: 2px;
  background-color: #4a5568;
}

.timeline-item-compact {
  position: relative;
  margin-bottom: 20px;
}

.timeline-icon-compact {
  position: absolute;
  left: 0;
  top: 50%;
  transform: translateY(-50%);
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: #2d3748;
  border: 2px solid #4a5568;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.25rem;
  color: #cbd5e0;
}

.timeline-content-compact {
  padding: 15px 20px;
  background-color: transparent;
  border-radius: 8px;
  border: 1px solid #4a5568;
  margin-left: 60px;
  transition: background-color 0.3s ease;
}

.timeline-content-compact:hover {
  background-color: rgba(59, 130, 246, 0.1);
}

@media (max-width: 768px) {
  .timeline-container-compact {
    padding-left: 40px;
  }

  .timeline-icon-compact {
    left: -15px;
    width: 30px;
    height: 30px;
    font-size: 1rem;
  }

  .timeline-content-compact {
    margin-left: 40px;
  }
}
</style>
