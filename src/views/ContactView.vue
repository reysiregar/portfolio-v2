<template>
  <transition name="fadeZoomOut">
    <section class="contact fade-zoom-out">
      <div class="container">
        <h1 class="contact-title">Let's Connect!</h1>
        <p class="contact-description">
          Send me a message and be sure to include your email,<br>
          so I can reach out if needed.
        </p>
        <form class="contact-form" @submit.prevent="showCaptcha">
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
            <textarea
              v-model="formData.message"
              rows="4"
              placeholder="Your Message"
              class="input-field textarea"
              required
            ></textarea>
          </div>

          <button 
            type="submit" 
            class="submit-btn"
            :disabled="isLoading"
          >
            {{ isLoading ? 'Sending...' : 'Send Message' }}
          </button>
        </form>

        <div class="social-links">
          <a href="https://wa.me/+6285179986368" target="_blank" class="social-icon">
            <i class="fab fa-whatsapp"></i>
          </a>
          <a href="https://t.me/vionite" target="_blank" class="social-icon">
            <i class="fab fa-telegram"></i>
          </a>
          <a href="https://instagram.com/reysiregars" target="_blank" class="social-icon">
            <i class="fab fa-instagram"></i>
          </a>
          <a href="https://www.linkedin.com/in/reynaldi-wiratama-siregar-490b8b261" target="_blank" class="social-icon">
            <i class="fab fa-linkedin"></i>
          </a>
        </div>
      </div>

      <!-- Captcha Modal -->
      <div v-if="showCaptchaModal" class="modal-overlay" @click.self="closeCaptchaModal">
        <div class="modal-content">
          <div class="modal-header">
            <h2>Please verify you're human</h2>
            <button class="close-btn" @click="closeCaptchaModal">&times;</button>
          </div>
          <div id="recaptcha-container" class="recaptcha-container"></div>
        </div>
      </div>
    </section>
  </transition>
</template>

<script>
import emailjs from '@emailjs/browser';
import Swal from 'sweetalert2';

export default {
  name: "ContactView",
  data() {
    return {
      formData: {
        name: '',
        message: ''
      },
      isLoading: false,
      showCaptchaModal: false,
      recaptchaWidget: null
    }
  },
  methods: {
    showCaptcha() {
      this.showCaptchaModal = true;
      // Initialize reCAPTCHA when modal opens
      this.$nextTick(() => {
        if (window.grecaptcha) {
          this.renderRecaptcha();
        } else {
          window.recaptchaCallback = this.renderRecaptcha;
        }
      });
    },
    closeCaptchaModal() {
      this.showCaptchaModal = false;
      // Reset reCAPTCHA if it exists
      if (this.recaptchaWidget !== null) {
        window.grecaptcha.reset(this.recaptchaWidget);
      }
    },
    renderRecaptcha() {
      if (!this.recaptchaWidget && document.getElementById('recaptcha-container')) {
        this.recaptchaWidget = window.grecaptcha.render('recaptcha-container', {
          sitekey: '6LfdSr4qAAAAADmRnhI8yVjubblG6FAf6i-0bK2n',
          theme: 'dark',
          callback: this.onCaptchaVerified
        });
      }
    },
    async onCaptchaVerified(captchaResponse) {
      // Close the modal
      this.showCaptchaModal = false;
      
      try {
        this.isLoading = true;
        
        const serviceId = 'service_4euvsrs';
        const templateId = 'template_muvt74j';
        const publicKey = 'HmOnXza70bkghQVKw';
        
        const templateParams = {
          from_name: this.formData.name,
          message: this.formData.message,
          to_name: 'Reynaldi',
          'g-recaptcha-response': captchaResponse
        };

        await emailjs.send(serviceId, templateId, templateParams, publicKey);
        
        await Swal.fire({
          title: 'Success!',
          text: 'Your message has been sent successfully.',
          icon: 'success',
          confirmButtonColor: '#1e90ff',
          background: '#1f1f1f',
          color: '#ffffff'
        });
        
        // Clear form
        this.formData = {
          name: '',
          message: ''
        };
        
      } catch (error) {
        console.error('Error sending email:', error);
        await Swal.fire({
          title: 'Error!',
          text: 'Failed to send message. Please try again later.',
          icon: 'error',
          confirmButtonColor: '#1e90ff',
          background: '#1f1f1f',
          color: '#ffffff'
        });
      } finally {
        this.isLoading = false;
      }
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

.recaptcha-container {
  display: flex;
  justify-content: center;
  margin: 20px 0;
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

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.75);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal-content {
  background: #1f1f1f;
  padding: 20px;
  border-radius: 10px;
  max-width: 400px;
  width: 90%;
}

.modal-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}

.modal-header h2 {
  font-size: 1.5rem;
  color: #f5f5f5;
  margin: 0;
}

.close-btn {
  background: none;
  border: none;
  color: #bbbbbb;
  font-size: 1.5rem;
  cursor: pointer;
  padding: 0 5px;
}

.close-btn:hover {
  color: #ffffff;
}

.recaptcha-container {
  display: flex;
  justify-content: center;
  margin: 20px 0;
}

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

  .modal-content {
    width: 95%;
  }

  .recaptcha-container {
    transform: scale(0.9);
    transform-origin: center;
  }
}
</style>