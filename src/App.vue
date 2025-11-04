<template>
  <div id="app">
    <nav class="navbar">
      <h1 class="logo">O.R.</h1>

      <div class="menu-toggle" @click="toggleMenu">
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </div>
      
      <ul :class="['nav-links', { active: isMenuOpen }]">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#education">Education</a></li>
        <li><a href="#experience">Experience</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>

    <section id="home" class="hero">
      <div class="hero-content">
        <h2>Hello, I'm <span>Octavia Rahmawati</span></h2>
        <p style="font-weight: 550; color: #f672bd;">Data Science | Data Analyst | Copy Writing | Content Writing</p>
        <button @click="scrollTo('projects')">Lihat Proyek Saya</button>
      </div>

      <div class="hero-image">
        <img src="./assets/6.jpg" alt="Octavia Rahmawati">
      </div>
    </section>

    <section id="about" class="about-section">
      <h2>About Me</h2>
      <p>I am a passionate self-challenger, data-driven problem solver, and endless learner. 
        I am a Bachelor Degree of Statistics who interested in the field of analysis and visualize, 
        especially in Data Science as part of being interested in Artificial Intelligence and Machine Learning.</p>
    </section>

    <section id="education" class="education-section">
      <h2>Education</h2>
      <div class="education-timeline">
        <div v-for="(edu, i) in education" :key="i" class="edu-card">
          <div class="edu-header">
            <img src="https://www.uii.ac.id/wp-content/uploads/2017/04/Logo-UII-Asli.png" alt="Logo" class="edu-logo" />
            <div class="edu-info">
              <h3>{{ edu.institution }}</h3>
              <p class="degree">{{ edu.degree }}</p>
              <p class="year">{{ edu.year }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="experience" class="experience-section">
      <h2>Experience & Certificates</h2>
      <div class="experience-grid">
        <div v-for="(exp, i) in experiences" :key="i" class="exp-card">
          <h3>{{ exp.title }}</h3>
          <p class="company">{{ exp.place }}</p>
          <p class="exp-year">{{ exp.year }}</p>

          <ul class="exp-list">
            <li v-for="(item, j) in exp.details" :key="j">{{ item }}</li>
          </ul>

          <a v-if="exp.link" :href="exp.link" target="_blank" class="cert-link">View Certificate</a>
        </div>
      </div>
    </section>

    <section id="skills" class="skills-section">
      <h2>Skills</h2>
      <div class="skills-grid">
        <div class="skill-card">
          <img src="https://cdn-icons-png.flaticon.com/512/5968/5968350.png" alt="Python" />
        </div>
        <div class="skill-card">
          <img src="https://cdn-icons-png.flaticon.com/512/2103/2103665.png" alt="R" />
        </div>
        <div class="skill-card">
          <img src="https://cdn-icons-png.flaticon.com/512/4248/4248443.png" alt="SQL" />
        </div>
        <div class="skill-card">
          <img id="tableau-icon" src="https://logos-world.net/wp-content/uploads/2021/10/Tableau-Logo.png" alt="Tableau" />
        </div>
        <div class="skill-card">
          <img src="https://cdn-icons-png.freepik.com/512/906/906342.png" alt="Power BI" />
        </div>
        <div class="skill-card">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS4I-sxWgEbArYbq5zFAmAEa0keDohrabo0Qw&s" alt="Minitab" />
        </div>
        <div class="skill-card">
          <img src="https://cdn-icons-png.flaticon.com/512/732/732220.png" alt="Microsoft Excel" />
        </div>
        <div class="skill-card">
          <img id="canvas-icon" src="https://static.vecteezy.com/system/resources/previews/048/759/334/non_2x/canva-transparent-icon-free-png.png" alt="Canva" />
        </div>
        <div class="skill-card">
          <img src="https://cdn-icons-png.flaticon.com/512/732/732224.png" alt="Microsoft PowerPoint" />
        </div>
      </div>
    </section>

    <section id="projects" class="projects-section">
      <h2>Projects</h2>
      <div class="projects">
        <!-- Daftar Project -->
        <div v-for="(p, i) in projects" :key="i" class="project-card">
          <a :href="p.link" target="_blank" class="project-title">{{ p.title }}</a>
          <p>{{ p.desc }}</p>
        </div>
      </div>
    </section>

    <section class="contact-section">
      <div id="contact" >
        <h2>Contact Me</h2>
        <div class="social-icons">
          <a href="mailto:octaviaarhmwt@gmail.com" target="_blank">
            <img src="https://cdn-icons-png.flaticon.com/512/281/281769.png" alt="Email" />
          </a>
          <a href="https://www.instagram.com/octaviaarhmwt" target="_blank">
            <img src="https://cdn-icons-png.flaticon.com/512/2111/2111463.png" alt="Instagram" />
          </a>
          <a href="https://www.linkedin.com/in/octaviaarhmwt" target="_blank">
            <img src="https://cdn-icons-png.flaticon.com/512/174/174857.png" alt="LinkedIn" />
          </a>
          <a href="https://medium.com/@octaviaarhmwt" target="_blank">
            <img src="https://cdn-icons-png.flaticon.com/512/5968/5968906.png" alt="Medium" />
          </a>
        </div>
      </div>
    </section>

    <footer>
      <p>© 2025 Octavia Rahmawati — All rights reserved.</p>
    </footer>
  </div>
</template>

<script setup>
import { ref } from "vue";

const isMenuOpen = ref(false);
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

export default {
  data() {
    return { menuActive: false };
  },
  methods: {
    toggleMenu() {
      this.menuActive = !this.menuActive;
    },
  },
};

const projects = [
  { 
    title: 'Object Counter Berbasis Convolutional Neural Network Pada Ruas Tugu Yogyakarta',
    link: 'https://medium.com/@octaviarahmawatii/object-counter-berbasis-convolutional-neural-network-pada-ruas-tugu-yogyakarta-c1d8fdb33563'
  },
  { 
    title: 'Simple Text Mining in R',
    link: 'https://medium.com/@octaviarahmawatii/simple-text-mining-in-r-92e6ddecd980'
  },
  { 
    title: 'Dashboard of The Highest Games Rating',
    link: 'https://medium.com/@octaviarahmawatii/menjadi-game-dengan-rating-tertinggi-apa-sebabnya-8afb4367cbdc'
  }
]

const scrollTo = (id) => {
  document.getElementById(id).scrollIntoView({ behavior: 'smooth' })
}

const education = [
  {
    institution: 'Universitas Islam Indonesia',
    degree: 'Bachelor of Statistics | Data Science Concentration',
    year: 'Sept 2020 - August 2024'
  },
]

const experiences = [
  {
    title: 'Data Analyst',
    place: 'Creative Data',
    year: 'March 2024 - July 2024',
    details: [
      'Managed projects involving Multiple Linear Regression and Random Forest algorithms to forecast car prices.',
      'Oversaw a project on Sentiment Analysis utilizing Support Vector Machine for the film "Queen of Tears".',
      'Created informative data visualizations such as graphs and diagrams, accompanied by thorough analysis interpretations to facilitate data-informed decision-making.'
    ]
  },
  {
    title: 'Statistics Consultant',
    place: 'Badan Pusat Statistik DIY',
    year: 'Jan 2023 - Feb 2023',
    details: [
      'Managed data inquiries on the BPS website and provided detailed consultations, offering tailored analytical approaches based on the dataset; successfully handled 1-2 projects weekly.',
      'Conducted comprehensive data analysis using various statistical techniques, including regression, time series analysis, forecasting, clustering, and classification.',
      'Acquired and processed large datasets, interpreted results through diverse tools, and presented insights and trends using engaging visual formats such as reports, infographics, and PowerPoint presentations.'
    ],
    link: '/certificates/Intern BPS.pdf'
  },
  {
    title: 'Data Analyst',
    place: 'Bayanaka Consultants',
    year: 'August 2022 - 2Dec 022',
    details: [
      'Conducted a survey on the consumption patterns of narcotics among rehabilitation patients at BNN DIY.',
      'Engaged in collaborative research with BNN DIY to investigate the impact of age, gender, occupation, and marital status on drug consumption patterns utilizing Chi-Square analysis.',
      'Employed Chi-Square and Mann-Whitney analyses to examine the effects of patient age, gender, lymphocyte count, Covid-19 status, and method of confirming Covid-19 on the diseases experienced.'
    ],
  },
]
</script>

<style scoped>
/* ====== Layout dasar ====== */
html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  font-family: 'Poppins', sans-serif;
  color: #222;
  background-color: #f9fafb;
  overflow-x: hidden;
}

/* ====== Navbar ====== */
.navbar {
  position: fixed;
  width: 90%;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  z-index: 1000;
  margin-top: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: rgba(248, 43, 156, 0.363);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.5);
  padding: 10px 30px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.05);
  border-radius: 50px;
}

.navbar-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 30px;
}
  
.logo {
  font-weight: 700;
  font-family: "Playfair Display", serif;
  color: #ffffff;
  font-size: 1.8rem;
}

.nav-links {
  position: absolute;
  list-style: none;
  display: flex;
  width: 100%;
  text-align: center;
  top: 70px;
  right: 0;
  border-radius: 15px;
  flex-direction: column;
  align-items: flex-start;
  padding: 15px 25px;
  gap: 35px;
  opacity: 0;
  pointer-events: none;
  transform: translateY(-10px);
  transition: all 0.3s ease;
  z-index: 5;
  font-family: "Playfair Display", serif;
  font-size: 1.1rem;
}

.nav-links li a {
  text-decoration: none;
  color: #ffffff;
  font-weight: 600;
  font-size: 1.1rem;
  transition: color 0.3s;
}

.nav-links a:hover {
  color: #f53eaf;
}

/* ===== Tombol hamburger ===== */
.menu-toggle {
  display: none;
  flex-direction: column;
  cursor: pointer;
  border-radius: 10px;
  padding: 8px;
}

.menu-toggle span {
  width: 25px;
  height: 3px;
  background: #fff;
  border-radius: 2px;
  transition: all 0.3s ease;
}

.bar {
  height: 3px;
  width: 25px;
  background-color: white;
  margin: 4px 0;
  border-radius: 3px;
}

/* ===== Responsif Navbar ===== */
@media (max-width: 768px) {
  .menu-toggle {
    display: flex;
    font-size: 26px;
    color: white;
    cursor: pointer;
  }

  .logo {
    font-size: 20px;
  }
  
  .navbar {
    display: flex;
    justify-content: space-between; /* biar logo & hamburger sejajar */
    align-items: center;
    flex-direction: row; /* jangan column */
    padding: 10px 20px;
  }

  .nav-links {
    position: absolute;
    display: none;
    width: 100%;
    text-align: center;
    top: 60px;
    right: 20px;
    background: rgba(248, 43, 156, 0.9);
    border-radius: 15px;
    flex-direction: column;
    align-items: flex-start;
    padding: 15px 25px;
    gap: 15px;
    opacity: 0;
    pointer-events: none;
    transform: translateY(-10px);
    transition: all 0.3s ease;
  }

  .nav-links.active {
    opacity: 1;
    pointer-events: auto;
    transform: translateY(0);
    display: flex;
  }
  
  .nav-links a {
    font-size: 0.9rem;
  }
}

/* Jangan ubah tampilan laptop */
@media only screen and (min-width: 769px) {
  .menu-toggle {
    display: none;
  }

  .nav-links {
    position: static;
    background: none;
    opacity: 1;
    pointer-events: auto;
    transform: none;
  }
}

.section {
  min-height: 100vh;
  display: block;                
  flex-direction: column;       
  align-items: center;          
  justify-content: center;      
  text-align: center;           
  padding: 40px 20px;
  scroll-snap-align: start;
}

.alt {
  background-color: #eef3f8;
}

.section h2 {
  font-size: 28px;
  margin-bottom: 20px;
  color: #111;
}

.section.hero {
  display: flex !important;
  align-items: center;
  justify-content: space-between;
}

/* ====== Hero ====== */
.hero {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  padding: 0 6vw;
  background-image: url('https://i.pinimg.com/736x/8d/4d/8c/8d4d8c621674afec6cb775138c315500.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  color: white;
  caret-color: transparent;
  user-select: none;
  outline: none;
}

/* Bagian teks */
.hero-content {
  align-items: center;
  justify-content: space-between;
  max-width: 60%;
  width: 100%;
  color: #ffffff;
  margin-top: 100px;
}

.hero h2 {
  font-size: 2.5rem;
  margin-bottom: 5px;
  font-weight: 700;
}

.hero span {
  font-weight: 700;
  font-size: 4rem;
  color: #fb0097;
  font-family: "Playfair Display", serif;
}

.hero-content p {
  font-size: 1.2rem;
}

.hero-content button {
  margin-top: 40px;
  background: white;
  color: #f454c4;
  border: none;
  padding: 12px 25px;
  border-radius: 30px;
  cursor: pointer;
  font-family: "Playfair Display", serif;
  font-size: 0.9rem;
  font-weight: 900;
  transition: 0.3s;
}

.hero-content button:hover {
  background: #fddcec;
}

/* Bagian gambar di kanan */
.hero-image {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 100px;
}

.hero-image img {
  width: 350px;
  height: 450px;
  object-fit: cover;
  border-radius: 180px 180px 0 0; /* melengkung di atas */
  box-shadow: 0 10px 60px rgba(0, 0, 0, 0.25);
  background: white;
  padding: 8px;
}

/* Responsif untuk HP/tablet */
@media (max-width: 768px) {
  .hero {
    flex-direction: column;
    text-align: center;
    padding: 80px 0px;
    height: auto;
  }

  .hero-image {
    margin-top: 40px;
  }

  .hero-image img {
    width: 200px;
    height: 250px;
  }
}

/* ====== About Me ====== */
.about-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  text-align: center;
  padding: 80px 20px;
  font-family: "Playfair Display", serif;

  background-image: url('https://i.pinimg.com/736x/8d/4d/8c/8d4d8c621674afec6cb775138c315500.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  overflow: hidden;
}

/* Judul */
.about-section h2 {
  font-size: 3rem;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 20px;
  position: relative;
}

.about-section h2::after {
  content: "";
  display: block;
  width: 60px;
  height: 3px;
  background: #ff0084;
  margin: 10px auto 0;
  border-radius: 2px;
}

/* Deskripsi */
.about-section p {
  max-width: 800px;
  font-size: 1.5rem;
  line-height: 1.8;
  color: #ffffff;
}

/* Responsif untuk HP */
@media (max-width: 768px) {
  .about-section h2 {
    font-size: 3rem;
  }

  .about-section p {
    font-size: 1.2rem;
    padding: 0 10px;
  }
}

/* ====== Education Section ====== */
.education-section {
  min-height: 100vh;
  text-align: center;
  padding: 100px 40px;
  background-image: url('https://i.pinimg.com/736x/8d/4d/8c/8d4d8c621674afec6cb775138c315500.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  font-family: "Playfair Display", serif;
  color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  caret-color: transparent;
  user-select: none;
  outline: none;
}

/* ====== Education with Logo ====== */
.edu-header {
  display: flex;
  align-items: center;
  gap: 25px;
}

.edu-logo {
  width: 100px;
  height: 100px;
  object-fit: contain;
  background: rgb(255, 255, 255);
  border-radius: 20px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.2);
}

.edu-info {
  text-align: left;
}

@media (max-width: 768px) {
  .edu-header {
    flex-direction: column;
    text-align: center;
  }

  .edu-logo {
    width: 70px;
    height: 70px;
  }

  .edu-info {
    text-align: center;
  }
}

.education-section h2 {
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 50px;
  position: relative;
}

.education-timeline {
  display: flex;
  flex-direction: column;
  gap: 30px;
  align-items: center;
}

.edu-card {
  background: rgba(255, 255, 255, 0.662);
  backdrop-filter: blur(10px);
  border-radius: 15px;
  padding: 25px 40px;
  width: 70%;
  box-shadow: 0 5px 15px rgba(0,0,0,0.2);
  transition: transform 0.3s ease;
}

.edu-card:hover {
  transform: translateY(-5px);
}

.edu-card h3 {
  color: #ff0099;
  font-size: 1.8rem;
}

.degree, .year {
  color: #fc5ebd;
  font-size: 1.3rem;
  font-weight: 600;
  margin: 5px 0;
}

/* ====== Experience Section ====== */
.experience-section {
  min-height: 100vh;
  text-align: center;
  padding: 100px 60px;
  background-image: url('https://i.pinimg.com/736x/8d/4d/8c/8d4d8c621674afec6cb775138c315500.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  font-family: "Playfair Display", serif;
  color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  caret-color: transparent;
  user-select: none;
  outline: none;
}

.experience-section h2 {
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 40px;
}

.experience-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
  justify-content: center;
  align-items: stretch;
}

.exp-card {
  background: rgba(255, 255, 255, 0.826);
  backdrop-filter: blur(10px);
  border-radius: 15px;
  padding: 30px 25px;
  box-shadow: 0 4px 15px rgba(0,0,0,0.2);
  transition: transform 0.3s ease;
  text-align: left;
}

.exp-card:hover {
  transform: translateY(-5px);
}

.exp-card h3 {
  color: #ff0099;
  font-size: 1.5rem;
  margin-bottom: 5px;
}

.company {
  font-weight: 600;
  font-size: 1.2rem;
  color: #ff4fb9;
}

.exp-list {
  margin: 10px 0 15px 18px;
  padding-left: 10px;
  color: #ff4fb9;
  font-size: 1rem;
  font-weight: 500;
  line-height: 1.6;
}

.exp-list li {
  list-style-type: disc;
  margin-bottom: 6px;
}

.exp-year {
  color: #ff4fb9;
  font-size: 1.2rem;
}

@media (max-width: 768px) {
  .exp-list {
    margin-left: 15px;
    font-size: 0.95rem;
  }
}

.cert-link {
  color: #ac0067ec;
  text-decoration: none;
  font-weight: bold;
  transition: 0.3s;
}

.cert-link:hover {
  text-decoration: underline;
  color: #fff;
}

/* Responsif */
@media (max-width: 768px) {
  .edu-card, .exp-card {
    width: 90%;
  }

  .education-section h2,
  .experience-section h2 {
    font-size: 2.5rem;
  }
}

/* ====== Skills ====== */
.skills-section {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  text-align: center;
  min-height: 100vh;
  font-family: "Playfair Display", serif;
  gap: 30px;
  /* padding: 100px 50px; */
  
  background-image: url('https://i.pinimg.com/736x/8d/4d/8c/8d4d8c621674afec6cb775138c315500.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  caret-color: transparent;
  user-select: none;
}

.skills-section h2 {
  font-size: 3rem;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 20px;
  position: relative;
}

#tableau-icon {
  width: 100px;
  height: 100px;
}

#canvas-icon {
  width: 120px;
  height: 120px;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
  gap: 30px;
  justify-items: center;
  width: 100%;
  max-width: 800px;
  margin-top: 40px;
}

.skill-card {
  background: white;
  border-radius: 25px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  width: 130px;
  height: 130px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  transition: all 0.3s ease;
  cursor: pointer;
  text-align: center;
}

.skill-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 20px rgba(0,0,0,0.15);
}

.skill-card img {
  width: 70px;
  height: 70px;
  object-fit: contain;
  filter: drop-shadow(0 2px 4px rgba(0,0,0,0.2));
  transition: transform 0.3s ease;
}

.skill-card img:hover {
  transform: scale(1.1);
}

/* Responsif */
@media (max-width: 768px) {
  .skill-card {
    width: 130px;
    height: 120px;
  }

  .skill-card img {
    width: 60px;
    height: 60px;
  }

  .skill-card p {
    font-size: 0.9rem;
  }
}

/* ====== Projects ====== */
.projects-section {
  text-align: center;
  min-height: 100vh;
  padding: 100px 60px;
  font-family: "Playfair Display", serif;
  background-image: url('https://i.pinimg.com/736x/8d/4d/8c/8d4d8c621674afec6cb775138c315500.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  caret-color: transparent;
  user-select: none;
}

.projects {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 30px;
  margin-top: 40px;
}

.projects-section h2 {
  font-size: 3rem;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 20px;
  position: relative;
}

.project-title {
  display: block;
  font-weight: 700;
  font-size: 20px;
  color: #ff18b6;
  text-decoration: none;
  text-align: center;
  transition: color 0.3s ease;
  caret-color: transparent;
  user-select: none;
  outline: none;
}

.project-title:hover {
  color: #268fff;
}

.project-card {
  background: white;
  border-radius: 15px;
  padding: 25px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  width: 270px;
  transition: 0.3s;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  align-items: center;
}

.project-card:hover {
  transform: translateY(-5px);
}

/* ====== Contact ====== */
.contact-section {
  background-image: url('https://i.pinimg.com/736x/8d/4d/8c/8d4d8c621674afec6cb775138c315500.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 40px 0;
}

#contact {
  background: rgba(255, 255, 255, 0.32);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  border-radius: 20px;
  padding: 90px 60px;
  text-align: center;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
  max-width: 600px;
  width: 80%;
}

#contact h2 {
  font-size: 2.4rem;
  margin-bottom: 20px;
  color: #fffafe;
  font-weight: 700;
  letter-spacing: 1px;
  font-family: "Playfair Display", serif;
}

#contact p {
  font-size: 1.2rem;
  color: #222;
  line-height: 1.6;
}

#contact a {
  color: #007bff;
  text-decoration: none;
  font-weight: 600;
  transition: color 0.3s ease;
}

#contact a:hover {
  color: #0056b3;
  text-decoration: underline;
}

.social-icons {
  display: flex;
  justify-content: center;
  gap: 60px;
  flex-wrap: wrap;
  margin-top: 30px;
  caret-color: transparent;
  user-select: none;
  outline: none;
}

.social-icons img {
  width: 50px;
  height: 50px;
  transition: transform 0.3s ease;
}

.social-icons img:hover {
  transform: scale(1.2);
}

/* Tambahan efek animasi saat di-scroll */
@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

#contact {
  animation: fadeInUp 1s ease;
}

/* ====== MEDIA QUERIES UNTUK RESPONSIVE ====== */

/* Tablet dan HP besar (maks 768px) */
@media only screen and (max-width: 768px) {
  #contact {
    padding: 60px 30px;
    width: 90%;
  }

  #contact h2 {
    font-size: 1.8rem;
  }

  .social-icons {
    gap: 40px;
  }

  .social-icons img {
    width: 45px;
    height: 45px;
  }
}

/* HP kecil (maks 480px) */
@media only screen and (max-width: 480px) {
  #contact {
    padding: 40px 20px;
  }

  #contact h2 {
    font-size: 1.6rem;
  }

  .social-icons {
    flex-wrap: wrap;
    gap: 25px;
  }

  .social-icons img {
    width: 40px;
    height: 40px;
  }
}

/* JANGAN GANGGU LAYAR BESAR */
@media only screen and (min-width: 769px) {
  #contact {
    padding: 90px 60px;
    max-width: 600px;
    width: 80%;
  }

  #contact h2 {
    font-size: 2.4rem;
  }

  .social-icons img {
    width: 50px;
    height: 50px;
  }
}

/* ====== Footer ====== */
footer {
  text-align: center;
  padding: 40px;
  background: #ff6ab9;
  color: hsl(0, 0%, 100%);
  font-size: 20px;
}

/* ===== Extra Responsif HP kecil ===== */
@media (max-width: 480px) {
  .logo {
    font-size: 1.3rem;
  }

  .hero span {
    font-size: 2rem;
  }

  .about-section p {
    font-size: 1rem;
  }

  .edu-card,
  .exp-card,
  .project-card {
    width: 100%;
  }
}

/* ====== Optional: smooth snapping ====== */
html, body {
  scroll-snap-type: y mandatory;
  overflow-y: scroll;
}
</style>
