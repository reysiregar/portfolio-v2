<template>
  <transition name="fadeZoomOut">
    <section class="contact fade-zoom-out">
      <div class="container">
        <!-- Page Title -->
        <h1 class="contact-title">Let's Connect</h1>
        <p class="contact-description">
          Send me a message and I'll get back to you soon.
        </p>
        <!-- Contact Form -->
        <form class="contact-form" @submit.prevent="handleSubmit">
          <!-- Input Fields -->
          <div class="input-wrapper">
            <input
              v-model="formData.name"
              type="text"
              placeholder="Your Name"
              class="input-field"
              required
            />
          </div>
          <div class="input-wrapper">
            <input
              v-model="formData.email"
              type="email"
              placeholder="Your Email"
              class="input-field"
              required
            />
          </div>
          <div class="input-wrapper">
            <textarea
              v-model="formData.message"
              rows="4"
              placeholder="Your Message"
              class="input-field textarea"
              required
            ></textarea>
          </div>
          <!-- Submit Button -->
          <button type="submit" class="submit-btn">Send Message</button>
        </form>

        <!-- Social Media Links -->
        <div class="social-links">
          <a href="https://t.me/vionite" target="_blank" class="social-icon">
            <i class="fab fa-telegram"></i>
          </a>
          <a href="https://instagram.com/reysiregars" target="_blank" class="social-icon">
            <i class="fab fa-instagram"></i>
          </a>
          <a href="https://wa.me/+6285179986368" target="_blank" class="social-icon">
            <i class="fab fa-whatsapp"></i>
          </a>
        </div>
      </div>
    </section>
  </transition>
</template>

<script>
export default {
  name: "ContactView",
  data() {
    return {
      formData: {
        name: '',
        email: '',
        message: ''
      }
    }
  },
  methods: {
    handleSubmit() {
      const yourEmail = 'reynaldisiregar24@yahoo.com';
      const subject = `Message from ${this.formData.name}`;
      const body = `Name: ${this.formData.name}
Email: ${this.formData.email}

Message:
${this.formData.message}`;

      const mailtoUrl = `mailto:${yourEmail}?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
      
      // Open email client
      window.location.href = mailtoUrl;

      // Clear the form by resetting formData
      this.formData = {
        name: '',
        email: '',
        message: ''
      };

      // Refresh the page after a short delay (to ensure email client opens)
      setTimeout(() => {
        window.location.reload();
      }, 100);
    }
  }
};
</script>

<style scoped>
@keyframes fadeZoomOut {
  0% {
    opacity: 0;
    transform: scale(0.8) translateY(30px);
  }
  100% {
    opacity: 1;
    transform: scale(1) translateY(0);
  }
}

.fade-zoom-out {
  animation: fadeZoomOut 0.8s ease-in-out;
}

.contact {
  background: #141414;
  color: #ffffff;
  min-height: 80vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 0 20px;
  box-sizing: border-box;
}

.container {
  max-width: 600px;
  width: 100%;
  text-align: center;
  padding: 40px 20px;
}

.contact-title {
  font-size: 2.5rem;
  font-weight: 600;
  margin-bottom: 10px;
  color: #f5f5f5;
}

.contact-description {
  font-size: 1rem;
  margin-bottom: 30px;
  color: #bbbbbb;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.input-wrapper {
  position: relative;
}

.input-field {
  width: 100%;
  padding: 10px 12px;
  border: 1px solid transparent;
  background-color: #1f1f1f;
  color: #ffffff;
  font-size: 1rem;
  border-radius: 20px;
  outline: none;
  transition: all 0.3s ease;
}

.input-field:hover,
.input-field:focus {
  border-color: #1e90ff;
  box-shadow: 0 0 8px rgba(30, 144, 255, 0.5);
  background-color: #222;
}

.input-field::placeholder {
  color: #777;
}

.textarea {
  resize: none;
}

.submit-btn {
  background-color: #1e90ff;
  color: #ffffff;
  border: none;
  padding: 12px;
  border-radius: 20px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.2s ease;
}

.submit-btn:hover {
  background-color: #1c7cd6;
  transform: translateY(-3px);
}

.submit-btn:active {
  transform: translateY(1px);
}

/* Social Media Links Styling */
.social-links {
  margin-top: 30px;
  display: flex;
  justify-content: center;
  gap: 20px;
}

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

/* Responsive Design */
@media (max-width: 768px) {
  .contact-title {
    font-size: 2rem;
  }
  
  .contact-description {
    font-size: 0.9rem;
  }
  
  .input-field {
    font-size: 0.9rem;
    padding: 8px 10px;
  }
}
</style>