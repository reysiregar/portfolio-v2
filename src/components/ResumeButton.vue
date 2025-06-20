<template>
  <a
    :href="resumePath"
    download="CV_REYNALDI_SIREGAR.pdf"
    class="resume-button"
    aria-label="Download my CV"
  >
    <svg 
      xmlns="http://www.w3.org/2000/svg" 
      viewBox="0 0 24 24" 
      fill="currentColor" 
      class="icon"
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
    <span>Download CV</span>
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
  }
}
</script>

<style scoped>
.resume-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 0.625rem 1.25rem;
  margin: 0;
  font-size: 0.875rem;
  font-weight: 500;
  color: #add8e6;
  background-color: transparent;
  border: 1px solid #add8e6;
  border-radius: 0.5rem;
  text-decoration: none;
  transition: background-color 0.3s, color 0.3s, transform 0.2s;
}

.resume-button:hover {
  background-color: rgba(173, 216, 230, 0.1);
  transform: translateY(-2px);
}

.resume-button:focus {
  outline: none;
  box-shadow: 0 0 0 3px rgba(173, 216, 230, 0.4);
}

.resume-button .icon {
  margin-right: 0.5rem;
  width: 1rem;
  height: 1rem;
}

@media (min-width: 768px) {
  .resume-button {
    margin: 0;
  }
}
</style>