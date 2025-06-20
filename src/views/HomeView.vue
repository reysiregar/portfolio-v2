<template>
  <main class="mt-6 md:mt-1 flex flex-col-reverse gap-8 items-center md:flex-row md:gap-16 md:justify-center min-h-[65vh] md:min-h-[80vh]">
    <div class="space-y-2 text-center md:text-left px-10">
      <p class="text-blue-200 animate-fade-up">Hello World, I'm</p>
      <h1 class="text-4xl font-bold md:text-5xl text-white animate-fade-up">Reynaldi Siregar</h1>
      <div class="py-2">
        <TypeWriter 
          :phrases="roles"
          :period="2000"
          class="text-xl font-semibold text-transparent bg-clip-text bg-gradient-to-r from-slate-100 to-blue-500 md:text-2xl animate-fade-up"
        />
      </div>
      <p class="text-white pr-4 animate-fade-up">
        Welcome to My portfolio website. 
        <span class="wave" role="img" aria-label="Waving hand emoji">👋🏼</span>
      </p>
      <br>
      <ResumeButton 
        :resume-path="resumePath"
        class="animate-fade-bot"
      />
    </div>
    <div class="flex justify-center md:justify-start animate-fade-right">
      <img 
        alt="Reynaldi Siregar's profile picture" 
        fetchpriority="high" 
        width="300" 
        height="300" 
        decoding="async" 
        class="w-10/12 md:h-auto rounded-full profile-picture" 
        src="/img/profile.jpg"
      >
    </div>
  </main>
</template>

<script>
import { defineComponent } from 'vue'
import TypeWriter from '../components/TypeWriter.vue'
import ResumeButton from '../components/ResumeButton.vue'

export default defineComponent({
  name: 'HomeView',
  components: {
    TypeWriter,
    ResumeButton
  },
  data() {
    return {
      roles: [
        "Front-End Developer",
        "Website Developer",
        "Information System Student",
        "IT Enthusiast"
      ],
      resumePath: '/CV_REYNALDI_SIREGAR.pdf',
    }
  }
})
</script>

<style scoped>
.profile-picture {
  box-shadow: 0 0 clamp(20px, 5vw, 40px) -5px var(--profile-shadow-color);
}

.wave {
  animation: wave-animation 2.5s infinite;
  transform-origin: 70% 70%;
  display: inline-block;
}

@keyframes wave-animation {
  0% { transform: rotate(0deg); }
  10% { transform: rotate(14deg); }
  20% { transform: rotate(-8deg); }
  30% { transform: rotate(14deg); }
  40% { transform: rotate(-4deg); }
  50% { transform: rotate(10deg); }
  60%, 100% { transform: rotate(0deg); }
}

.animate-fade-up {
  animation: fadeUp var(--animation-duration) forwards;
  animation-delay: var(--animation-delay);
  opacity: 0;
}

.animate-fade-right {
  animation: fadeRight var(--animation-duration) forwards;
  animation-delay: var(--animation-delay);
  opacity: 0;
}

.animate-fade-bot {
  animation: fadeBot var(--animation-duration) forwards;
  animation-delay: var(--animation-delay);
  opacity: 0;
}

@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translate3d(0, 100%, 0);
  }
  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}

@keyframes fadeRight {
  from {
    opacity: 0;
    transform: translateX(100%);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeBot {
  from {
    opacity: 0;
    transform: translate3d(0, -100%, 0);
  }
  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}

@media (prefers-reduced-motion: reduce) {
  .animate-fade-up,
  .animate-fade-right,
  .animate-fade-bot,
  .wave {
    animation: none;
    opacity: 1;
  }
}
</style>