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
      
      <section class="certificates-container fade-zoom-in">
        <div v-for="cert in certificates" :key="cert.id" class="certificate-article">
          <div class="article-wrapper">
            <figure>
              <img 
                :alt="cert.name" 
                loading="lazy" 
                decoding="async"
                :src="'/img/certificates/' + cert.imageUrl + '.jpg'"
              >
            </figure>
            <div class="article-body">
              <h2>{{ cert.name }}</h2>
              <p class="issuer-info">
                Issued by {{ cert.issuer }} • {{ cert.issueDate }}
              </p>
              <p class="topics-info">
                {{ cert.topics }}
              </p>
              <a 
                :href="cert.credentialUrl" 
                target="_blank" 
                rel="noreferrer"
                class="view-credential"
              >
                View Credential 
                <span class="sr-only">for {{ cert.name }}</span>
                <svg xmlns="http://www.w3.org/2000/svg" class="icon" viewBox="0 0 20 20" fill="currentColor">
                  <path fill-rule="evenodd" d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
                </svg>
              </a>
            </div>
          </div>
        </div>
      </section>
    </article>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
/* Certificate Card Styling */
.certificates-container {
  display: grid;
  max-width: 1200px;
  margin-inline: auto;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 24px;
  padding-bottom: 32px;
}

.certificate-article {
  --img-scale: 1.001;
  --title-color: #e2e8f0;
  --link-icon-translate: -20px;
  --link-icon-opacity: 0;
  position: relative;
  border-radius: 16px;
  box-shadow: none;
  background: #1e1e1f;
  transform-origin: center;
  transition: all 0.4s ease-in-out;
  overflow: hidden;
  border: 1px solid #383838;
  font-family: 'Poppins', sans-serif;
}

.certificate-article a::after {
  position: absolute;
  inset-block: 0;
  inset-inline: 0;
  cursor: pointer;
  content: "";
}

.certificate-article h2 {
  margin: 0 0 12px 0;
  font-size: 1.2rem;
  font-weight: 600;
  color: var(--title-color);
  transition: color 0.3s ease-out;
}

.certificate-article figure {
  margin: 0;
  padding: 0;
  aspect-ratio: 16 / 9;
  overflow: hidden;
}

.certificate-article img {
  max-width: 100%;
  transform-origin: center;
  transform: scale(var(--img-scale));
  transition: transform 0.4s ease-in-out;
  object-fit: contain;
}

.article-body {
  padding: 24px;
}

.certificate-article a {
  display: inline-flex;
  align-items: center;
  text-decoration: none;
  color: #60a5fa;
  margin-top: 8px;
}

.certificate-article a:focus {
  outline: 1px dotted #60a5fa;
}

.certificate-article a .icon {
  min-width: 24px;
  width: 24px;
  height: 24px;
  margin-left: 5px;
  transform: translateX(var(--link-icon-translate));
  opacity: var(--link-icon-opacity);
  transition: all 0.3s;
}

.certificate-article:hover {
  --img-scale: 1.1;
  --title-color: #60a5fa;
  --link-icon-translate: 0;
  --link-icon-opacity: 1;
  box-shadow: rgba(0, 0, 0, 0.3) 0px 10px 36px 0px, rgba(0, 0, 0, 0.2) 0px 0px 0px 1px;
  background: #282828;
  transform: translateY(-5px);
}

.issuer-info {
  font-size: 0.7rem;
  color: #c1c1c1;
  margin-bottom: 12px;
}

.topics-info {
  font-size: 0.8rem;
  color: #93c5fd;
  margin-bottom: 16px;
}


.view-credential {
  font-size: 0.85rem;
  font-weight: 500;
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

/* Animation */
@keyframes fadeZoomIn {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

.fade-zoom-in {
  animation: fadeZoomIn 1s ease-in-out;
}

/* Responsive Layout */
@media screen and (max-width: 768px) {
  .certificate-article {
    container: card/inline-size;
  }
}

@container card (min-width: 380px) {
  .article-wrapper {
    display: grid;
    grid-template-columns: 120px 1fr;
    gap: 16px;
  }
  
  .article-body {
    padding-left: 0;
  }
  
  figure {
    width: 100%;
    height: 100%;
    overflow: hidden;
  }
  
  figure img {
    height: 100%;
    aspect-ratio: 1;
    object-fit: cover;
  }
}
</style>