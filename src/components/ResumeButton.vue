<template>
    <a
      :href="resumePath"
      download="Resume_Reynaldi_Wiratama_Siregar.pdf"
      class="flex items-center py-2 px-4 mx-auto text-sm font-medium rounded-lg border transition duration-300 md:py-2.5 md:px-5 md:mx-0 text-blue-200 border-blue-200 hover:bg-blue-200 hover:bg-opacity-10 bg-transparent focus:outline-none focus:ring-2 focus:ring-blue-200 focus:ring-opacity-50 w-fit"
      @click="trackDownload"
    >
      <svg 
        xmlns="http://www.w3.org/2000/svg" 
        viewBox="0 0 24 24" 
        fill="currentColor" 
        class="mr-2 w-4 h-4"
        aria-hidden="true"
      >
        <path 
          fill-rule="evenodd" 
          d="M5.625 1.5H9a3.75 3.75 0 013.75 3.75v1.875c0 1.036.84 1.875 1.875 1.875H16.5a3.75 3.75 0 013.75 3.75v7.875c0 1.035-.84 1.875-1.875 1.875H5.625a1.875 1.875 0 01-1.875-1.875V3.375c0-1.036.84-1.875 1.875-1.875zm5.845 17.03a.75.75 0 001.06 0l3-3a.75.75 0 10-1.06-1.06l-1.72 1.72V12a.75.75 0 00-1.5 0v4.19l-1.72-1.72a.75.75 0 00-1.06 1.06l3 3z" 
          clip-rule="evenodd"
        />
        <path 
          d="M14.25 5.25a5.23 5.23 0 00-1.279-3.434 9.768 9.768 0 016.963 6.963A5.23 5.23 0 0016.5 7.5h-1.875a.375.375 0 01-.375-.375V5.25z"
        />
      </svg>
      <span>Download Resume</span>
    </a>
  </template>
  
  <script>
  export default {
    name: 'ResumeButton',
    props: {
      resumePath: {
        type: String,
        required: true
      }
    },
    methods: {
      trackDownload() {
        // Add analytics tracking if needed
        console.log('Resume download initiated')
      }
    }
  }
  </script>