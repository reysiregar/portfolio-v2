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
        }
      ]
    };
  }
}
</script>

<template>
  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-blue-50 mx-3">
    <article data-page="certificates">
      <header>
        <div class="text-2xl font-bold text-white mb-10 fadein-bot title-section flex items-center justify-center flex-col">
          <h4>My Certificates</h4>
          <h4 class="text-base font-normal text-transparent bg-clip-text bg-gradient-to-r from-slate-100 to-blue-300">
            Learning progress & achievements
          </h4>
        </div>
      </header>
      
      <section>
        <div>
          <div class="grid grid-cols-1 gap-4 pb-32 md:grid-cols-2 md:gap-3 xl:grid-cols-3 xl:gap-3 2xl:gap-5 fade-zoom-in">
            <div v-for="cert in certificates" :key="cert.id">
              <div class="item-card flex flex-col gap-2 rounded bg-[#1e1e1f] hover:bg-[#282828] border border-[#383838] rounded-xl text-blue-50 md:gap-3 px-5 py-5 lg:px-5 h-96">
                <div class="flex items-center justify-center h-40 w-full zoom-in">
                  <img 
                    :alt="cert.name" 
                    loading="lazy" 
                    decoding="async" 
                    class="drop-shadow-xl rounded rounded-xl w-full h-full object-contain"
                    :src="'/img/certificates/' + cert.imageUrl + '.jpg'"
                  >
                </div>
                
                <div class="w-full flex flex-col justify-between flex-grow gap-2 text-sm md:text-base lg:text-lg">
                  <div>
                    <div class="title-text font-medium text-secondary">{{ cert.name }}</div>
                    <div class="w-full text-left text-[10px] text-[#c1c1c1] md:text-xs lg:text-sm mt-2">
                      Issued by {{ cert.issuer }} • {{ cert.issueDate }}
                    </div>
                    <div class="w-full mt-4 text-normal text-sm text-left text-blue-200">
                      {{ cert.topics }}
                    </div>
                  </div>
                  
                  <div class="w-full flex justify-end mt-auto pt-4">
                    <div class="flex cursor-pointer items-end gap-2 text-primary">
                      <a 
                        :href="cert.credentialUrl" 
                        target="_blank" 
                        rel="noreferrer"
                        title="View credential" 
                        class="transition-all hover:text-accent"
                      >
                        <svg 
                          stroke="currentColor"
                          fill="none" 
                          stroke-width="2" 
                          viewBox="0 0 24 24" 
                          stroke-linecap="round" 
                          stroke-linejoin="round"
                          height="18" 
                          width="18" 
                          xmlns="http://www.w3.org/2000/svg"
                        >
                          <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                          <polyline points="15 3 21 3 21 9"></polyline>
                          <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                      </a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </article>
  </div>
</template>

<style>
.item-card:hover {
  transition: transform 0.3s ease;
  transform: translateY(-8px);
}

svg:hover {
  stroke: #add8e6;
}

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
</style>