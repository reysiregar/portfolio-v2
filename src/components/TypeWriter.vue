<template>
    <div 
      class="typewriter" 
      role="text" 
      :aria-label="`Current text: ${txt}`"
    >
      <span class="wrap">{{ txt }}</span>
    </div>
  </template>
  
  <script>
  export default {
    name: 'TypeWriter',
    props: {
      phrases: {
        type: Array,
        required: true,
        validator: (value) => value.length > 0
      },
      period: {
        type: Number,
        default: 2000
      }
    },
    data() {
      return {
        txt: '',
        loopNum: 0,
        isDeleting: false
      }
    },
    created() {
      this.timeoutId = null
    },
    mounted() {
      this.txt = ''
      this.tick()
    },
    beforeUnmount() {
      if (this.timeoutId) {
        clearTimeout(this.timeoutId)
      }
    },
    methods: {
      tick() {
        const i = this.loopNum % this.phrases.length
        const fullTxt = this.phrases[i]
  
        this.txt = this.isDeleting 
          ? fullTxt.substring(0, this.txt.length - 1) 
          : fullTxt.substring(0, this.txt.length + 1)
  
        let delta = 200 - Math.random() * 100
  
        if (this.isDeleting) {
          delta /= 2
        }
  
        if (!this.isDeleting && this.txt === fullTxt) {
          delta = this.period
          this.isDeleting = true
        } else if (this.isDeleting && this.txt === '') {
          this.isDeleting = false
          this.loopNum++
          delta = 500
        }
  
        this.timeoutId = setTimeout(() => {
          requestAnimationFrame(this.tick)
        }, delta)
      }
    }
  }
  </script>
  
  <style scoped>
  .typewriter .wrap {
    border-right: 0.08em solid #fff;
    animation: blink-caret 1s ease-in-out infinite;
  }
  
  @keyframes blink-caret {
    from, to { border-color: transparent }
    50% { border-color: #fff }
  }
  
  @media (prefers-reduced-motion: reduce) {
    .typewriter .wrap {
      animation: none;
      border-right: none;
    }
  }
  </style>