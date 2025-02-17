// SocialLink.vue
<template>
  <a 
    :href="url" 
    :aria-label="label"
    target="_blank" 
    rel="noopener noreferrer"
    class="social-icon"
  >
    <i :class="icon"></i>
  </a>
</template>

<script>
export default {
  name: 'SocialLink',
  props: {
    url: {
      type: String,
      required: true
    },
    icon: {
      type: String,
      required: true
    },
    label: {
      type: String,
      required: true
    },
    platform: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
.social-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 45px;
  height: 45px;
  border-radius: 50%;
  background-color: #1e90ff;
  color: white;
  font-size: 1.5rem;
  transition: all 0.3s ease;
}

.social-icon:hover {
  background-color: #1c7cd6;
  transform: translateY(-3px);
}

.social-icon:active {
  transform: translateY(1px);
}
</style>