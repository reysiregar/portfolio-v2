<script>
export default {
  data() {
    return {
      certificates: [
        {
            id: 1,
            name: 'Belajar Dasar Pemrograman Web',
            issuer: 'Dicoding',
            issueDate: 'November 2024',
            imageUrl: 'sertifikat_course_1',
            credentialUrl: 'https://www.dicoding.com/certificates/1OP842VJ1ZQK',
            topics: 'React, Front-End Web'
        },
        {
            id: 2,
            name: 'Belajar Dasar Pemrograman JavaScript',
            issuer: 'Dicoding',
            issueDate: 'November 2024',
            imageUrl: 'sertifikat_course_2',
            credentialUrl: 'https://www.dicoding.com/certificates/07Z64DLN2PQR',
            topics: 'Google Cloud, React, Front-End Web, Back-End'
        },
        {
            id: 3,
            name: 'Belajar Membuat Front-End Web untuk Pemula',
            issuer: 'Dicoding',
            issueDate: 'November 2024',
            imageUrl: 'sertifikat_course_3',
            credentialUrl: 'https://www.dicoding.com/certificates/2VX34E134ZYQ',
            topics: 'React, Front-End Web'
        },
        {
            id: 4,
            name: 'Belajar Dasar AI',
            issuer: 'Dicoding',
            issueDate: 'November 2024',
            imageUrl: 'sertifikat_course_4',
            credentialUrl: 'https://www.dicoding.com/certificates/4EXG7240GPRL',
            topics: 'Artificial Intelligence, Machine Learning'
        },
        {
            id: 5,
            name: 'Problem Solving (Basic)',
            issuer: 'HackerRank',
            issueDate: 'July 2024',
            imageUrl: 'sertifikat_hackerrank_1',
            credentialUrl: 'https://www.hackerrank.com/certificates/34f5b92b171d',
            topics: 'Data Structures, Algorithms'
        },
        {
            id: 6,
            name: 'Fundamental Front-End Web Development',
            issuer: 'Dicoding',
            issueDate: 'February 2025',
            imageUrl: 'sertifikat_course_5',
            credentialUrl: 'https://www.dicoding.com/certificates/0LZ0RGW63P65',
            topics: 'API, Webpack, Front-End Web'
        },
        {
            id: 7,
            name: 'Intermediate Front-End Development',
            issuer: 'Dicoding',
            issueDate: 'March 2025',
            imageUrl: 'sertifikat_kelulusan',
            credentialUrl: 'https://www.dicoding.com/users/reysiregar',
            topics: 'Intermediate, Front-End'
        }
      ]
    };
  }
}
</script>

<template>
  <div class="px-5 py-5 md:px-12 md:py-10 text-left mx-3">
    <article data-page="certificates">
      <header>
        <div class="text-2xl font-bold text-white mb-10 fadein-bot title-section flex items-center justify-center flex-col">
          <h4>My Certificates</h4>
          <h4 class="text-base font-normal text-transparent bg-clip-text bg-gradient-to-r from-slate-100 to-blue-300">
            Learning progress & achievements
          </h4>
        </div>
      </header>
      
      <section class="certificates-container">
        <div 
          v-for="(cert, idx) in certificates" 
          :key="cert.id" 
          class="certificate-card fadein-smooth"
          :style="{ animationDelay: (0.12 * idx) + 's' }"
        >
          <figure class="card-image">
            <img 
              :alt="cert.name" 
              loading="lazy" 
              decoding="async"
              :src="'/img/certificates/' + cert.imageUrl + '.jpg'"
            >
          </figure>
          <div class="card-body">
            <div class="card-content">
              <h2 class="card-title">{{ cert.name }}</h2>
              <p class="issuer-info">
                {{ cert.issuer }} • {{ cert.issueDate }}
              </p>
              <p class="topics-info">
                {{ cert.topics }}
              </p>
            </div>
            <a 
              :href="cert.credentialUrl" 
              target="_blank" 
              rel="noreferrer"
              class="view-credential-btn"
            >
              View Credential
              <span class="sr-only">for {{ cert.name }}</span>
              <svg xmlns="http://www.w3.org/2000/svg" class="icon" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
              </svg>
            </a>
          </div>
        </div>
      </section>
    </article>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');

.certificates-container {
  display: grid;
  max-width: 1100px;
  margin-inline: auto;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 24px;
  padding-bottom: 32px;
}

.certificate-card {
  display: flex;
  flex-direction: column;
  align-items: stretch;
  background: #23232b;
  border-radius: 18px;
  box-shadow: 0 2px 12px 0 rgba(30,30,31,0.10);
  border: 1.5px solid #34344a;
  overflow: hidden;
  transition: box-shadow 0.3s cubic-bezier(.4,2,.6,1), transform 0.3s cubic-bezier(.4,2,.6,1), border 0.3s;
  padding: 0;
  min-height: 220px;
}
.certificate-card:hover {
  box-shadow: 0 8px 32px 0 rgba(60,130,246,0.18), 0 1.5px 8px 0 rgba(30,30,31,0.10);
  border: 1.5px solid #60a5fa;
  transform: scale(1.035);
  background: #232a36;
}

.card-image {
  width: 100%;
  aspect-ratio: 16/10;
  background: #18181b;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  border-bottom: 1px solid #34344a;
}
.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s cubic-bezier(.4,2,.6,1);
}
.certificate-card:hover .card-image img {
  transform: scale(1.07);
}

.card-body {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  height: 100%;
  padding: 8px 10px 6px 10px;
}
.card-content {
  flex: 1 1 auto;
}
.card-title {
  font-size: 1.08rem;
  font-weight: 600;
  color: #e2e8f0;
  margin-bottom: 8px;
  margin-top: 2px;
  line-height: 1.3;
}
.issuer-info {
  font-size: 0.78rem;
  color: #b3b3b3;
  margin-bottom: 6px;
}
.topics-info {
  font-size: 0.85rem;
  color: #7dd3fc;
  margin-bottom: 12px;
}

.view-credential-btn {
  display: flex;
  align-items: center;
  gap: 6px;
  background: #1e293b;
  color: #60a5fa;
  font-size: 0.97rem;
  font-weight: 600;
  border: none;
  border-radius: 8px;
  padding: 6px 12px 6px 10px;
  margin-top: 10px;
  margin-bottom: 0;
  margin-left: 0;
  box-shadow: 0 1px 4px 0 rgba(30,30,31,0.07);
  transition: background 0.2s, color 0.2s, box-shadow 0.2s, transform 0.2s;
  text-decoration: none;
  position: relative;
}
.view-credential-btn:focus {
  outline: 2px solid #60a5fa;
}
.certificate-card:hover .view-credential-btn {
  background: #2563eb;
  color: #fff;
  box-shadow: 0 2px 8px 0 rgba(60,130,246,0.13);
  transform: translateY(-2px) scale(1.04);
}
.view-credential-btn .icon {
  min-width: 20px;
  width: 20px;
  height: 20px;
  margin-left: 2px;
  transition: transform 0.3s, opacity 0.3s;
  transform: translateX(-8px);
  opacity: 0;
}
.certificate-card:hover .view-credential-btn .icon {
  transform: translateX(0);
  opacity: 1;
}

.sr-only:not(:focus):not(:active) {
  clip: rect(0 0 0 0); 
  clip-path: inset(50%);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap; 
  width: 1px;
}

/* Staggered smooth fade-in animation */
@keyframes fadeinSmooth {
  0% {
    opacity: 0;
    transform: translateY(30px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
.fadein-smooth {
  opacity: 0;
  animation: fadeinSmooth 0.8s cubic-bezier(.4,2,.6,1) forwards;
}

@media screen and (max-width: 768px) {
  .certificates-container {
    grid-template-columns: 1fr;
    gap: 18px;
  }
  .certificate-card {
    min-height: 140px;
  }
  .card-body {
    padding: 6px 6px 4px 6px;
  }
  .view-credential-btn {
    padding: 6px 8px 6px 8px;
    font-size: 0.93rem;
  }
}
</style>