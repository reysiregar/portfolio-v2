<template>
  <div class="preloader">
    <svg class="atom" width="120" height="120" viewBox="0 0 120 120">
      <defs>
        <filter id="glow" x="-30%" y="-30%" width="160%" height="160%">
          <feGaussianBlur stdDeviation="4" result="coloredBlur"/>
          <feMerge>
            <feMergeNode in="coloredBlur"/>
            <feMergeNode in="SourceGraphic"/>
          </feMerge>
        </filter>
      </defs>
      
      <!-- Nucleus -->
      <g class="nucleus-container">
        <circle class="nucleus" cx="60" cy="60" r="8" filter="url(#glow)" />
      </g>
      
      <!-- Orbits and Electrons -->
      <g class="orbit-container">
        <path id="orbit1" class="orbit" d="M 60, 60 m -50, 0 a 50,50 0 1,0 100,0 a 50,50 0 1,0 -100,0"></path>
        <path id="orbit2" class="orbit" transform="rotate(60 60 60)" d="M 60, 60 m -50, 0 a 50,50 0 1,0 100,0 a 50,50 0 1,0 -100,0"></path>
        <path id="orbit3" class="orbit" transform="rotate(120 60 60)" d="M 60, 60 m -50, 0 a 50,50 0 1,0 100,0 a 50,50 0 1,0 -100,0"></path>

        <circle class="electron" r="4">
            <animateMotion dur="3.5s" repeatCount="indefinite">
                <mpath xlink:href="#orbit1" />
            </animateMotion>
        </circle>
        <circle class="electron" r="4">
            <animateMotion dur="3.5s" repeatCount="indefinite" begin="-1.17s">
                <mpath xlink:href="#orbit2" />
            </animateMotion>
        </circle>
        <circle class="electron" r="4">
            <animateMotion dur="3.5s" repeatCount="indefinite" begin="-2.33s">
                <mpath xlink:href="#orbit3" />
            </animateMotion>
        </circle>
      </g>
    </svg>
  </div>
</template>

<script>
export default {
  name: 'AppPreloader',
};
</script>

<style scoped>
.preloader {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #1e1e1e;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.nucleus {
  fill: #add8e6;
}

.nucleus-container {
  transform-origin: center;
  animation: rotate-nucleus 3.5s infinite linear;
}

.orbit {
  fill: none;
  stroke: #add8e6;
  stroke-width: 1;
  opacity: 0.3;
}

.electron {
  fill: white;
  filter: url(#glow);
}

@keyframes rotate-nucleus {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style> 