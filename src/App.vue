<template>
  <div id="app">
    <nav>
      <a v-for="link in navLinks" :key="link.href" :href="link.href">{{ link.label }}</a>
    </nav>

    <header>
      <div class="hero">
        <div class="hero-text">
          <h1>{{ hero.name }}</h1>
          <p>{{ hero.tagline }}</p>
          <div class="status-badge"><span></span>{{ hero.status }}</div>
        </div>

        <div class="profile-card">
          <div class="profile-photo">
            <img :src="hero.profileImage" :alt="hero.name" />
          </div>
          <div class="profile-details">
            <p>{{ hero.profileText }}</p>
            <ul>
              <li v-for="item in hero.profilePoints" :key="item">{{ item }}</li>
            </ul>
          </div>
        </div>
      </div>
    </header>

    <section id="about">
      <h2>About Me</h2>
      <p>{{ about }}</p>
    </section>

    <section id="info">
      <h2>Personal Info</h2>
      <ul>
        <li v-for="info in personalInfo" :key="info">{{ info }}</li>
      </ul>
    </section>

    <section id="likes">
      <h2>Likes & Hobbies</h2>
      <ul>
        <li v-for="like in likes" :key="like">{{ like }}</li>
      </ul>
    </section>

    <section id="models">
      <h2>Role Models</h2>
      <ul>
        <li v-for="model in roleModels" :key="model">{{ model }}</li>
      </ul>
    </section>

    <section id="skills">
      <h2>Skills & Expertise</h2>
      <ul>
        <li v-for="skill in skills" :key="skill">{{ skill }}</li>
      </ul>
    </section>

    <section id="languages">
      <h2>Programming Languages</h2>
      <table class="languages-table">
        <thead>
          <tr>
            <th>Icon</th>
            <th>Language</th>
            <th>Years of Experience</th>
            <th>Number of Projects</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="language in languages" :key="language.name">
            <td class="language-icon-cell"><img :src="language.icon" :alt="language.name" class="language-icon"/></td>
            <td>{{ language.name }}</td>
            <td>{{ language.years }}</td>
            <td>{{ language.projects }}</td>
          </tr>
        </tbody>
      </table>
    </section>

    <section id="services">
      <h2>Services</h2>
      <ul>
        <li v-for="service in services" :key="service">{{ service }}</li>
      </ul>
    </section>

    <section id="contact">
      <h2>Contact</h2>
      <p>Email: {{ contact.email }}</p>
      <p>Instagram: {{ contact.instagram }}</p>
    </section>

    <section id="projects">
      <h2>Projects</h2>
      <div class="projects-container">
        <div class="project-card" v-for="project in projects" :key="project.title">
          <h3>{{ project.title }}</h3>
          <p>{{ project.description }}</p>
        </div>
      </div>
    </section>

    <footer>
      <div class="footer-container">
        <div class="footer-left">
          <h3>Contact</h3>
          <p>Email: {{ contact.email }}</p>
          <p>Location: {{ contact.location }}</p>
        </div>
        <div class="footer-center">
          <h3>Follow Me</h3>
          <div class="social-icons">
            <a
              v-for="item in socialLinks"
              :key="item.name"
              :href="item.url"
              :title="item.name"
              target="_blank"
              rel="noopener noreferrer"
            >
              <img :src="item.icon" :alt="item.name" />
            </a>
          </div>
        </div>
        <div class="footer-right">
          <h3>Portfolio</h3>
          <p>© {{ footer.year }} {{ footer.owner }}. All Rights Reserved.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
const navLinks = [
  { label: 'About', href: '#about' },
  { label: 'Personal Info', href: '#info' },
  { label: 'Likes', href: '#likes' },
  { label: 'Role Models', href: '#models' },
  { label: 'Skills', href: '#skills' },
  { label: 'Languages', href: '#languages' },
  { label: 'Contact', href: '#contact' },
  { label: 'Services', href: '#services' },
  { label: 'Projects', href: '#projects' }
];

const hero = {
  name: 'Shami Tonny',
  tagline: 'Student | Future Developer | Creative Thinker',
  status: 'Available to work',
  profileImage: '/sketch.png',
  profileText: 'Creative web builder with a passion for polished UI, smooth animation, and real results.',
  profilePoints: [
    'Open to freelance and full-time work',
    'Remote-ready and project-focused',
    'Fast learner with strong design sense'
  ]
};

const about = 'Hello! My name is Shami Tonny. I am passionate about technology, programming, and creativity. I enjoy building websites and learning modern development tools.';

const personalInfo = [
  'Name: Shami Tonny',
  'Occupation: Student',
  'Location: Rwanda',
  'Goal: Becoming a professional software developer'
];

const likes = ['Programming', 'Gaming', 'Basketball', 'Learning new technologies', 'Designing websites', 'Music'];
const roleModels = ['Tech Innovators', 'Successful Software Developers', 'Creative Designers'];
const skills = ['HTML', 'CSS', 'JavaScript', 'Vue.js (Learning)', 'Problem Solving', 'Leadership'];

const languages = [
  { name: 'HTML', icon: 'https://img.icons8.com/color/96/000000/html-5.png', years: '2 years', projects: '12+ projects' },
  { name: 'CSS', icon: 'https://img.icons8.com/color/96/000000/css3.png', years: '2 years', projects: '12+ projects' },
  { name: 'JavaScript', icon: 'https://img.icons8.com/color/96/000000/javascript.png', years: '1.5 years', projects: '8+ projects' },
  { name: 'Vue.js', icon: 'https://img.icons8.com/color/96/000000/vue-js.png', years: '6 months', projects: '3+ projects' },
  { name: 'Python', icon: 'https://img.icons8.com/color/96/000000/python.png', years: '1 year', projects: '5+ projects' },
  { name: 'React', icon: 'https://img.icons8.com/color/96/000000/react-native.png', years: '6 months (Learning)', projects: '2+ projects' }
];

const services = [
  'Web Development (HTML, CSS, JavaScript)',
  'Creative Design',
  'Problem Solving',
  'Team Collaboration',
  'Project Management',
  'Technical Support',
  'Helping companies go digital'
];

const contact = {
  email: 'tonnyshami2k25@gmail.com',
  instagram: '@shamy.tonn.25',
  location: 'Rwanda'
};

const projects = [
  { title: 'Restaurant Website', description: 'A full restaurant website with menu, booking, and responsive design.' },
  { title: 'TEMBERA URWANDA tourism app', description: 'A tourism app built with Vue.js home page, services page, about page, contact us page, gallery page and destinations page.' },
  { title: 'AI Idea generator', description: 'An AI based Idea generator which turns ideas into projects.' },
  { title: 'Portfolio Website', description: 'This personal portfolio showcasing my skills and projects.' }
];

const socialLinks = [
  { name: 'Instagram', url: 'https://instagram.com/shamy.tonn.25', icon: 'https://img.icons8.com/ios-filled/24/ffffff/instagram-new.png' },
  { name: 'GitHub', url: 'https://github.com/123TRELLIS', icon: 'https://img.icons8.com/ios-filled/24/ffffff/github.png' },
  { name: 'Gmail', url: 'mailto:tonnyshami2k25@gmail.com', icon: 'https://img.icons8.com/ios-filled/24/ffffff/gmail.png' }
];

const footer = {
  year: '2026',
  owner: 'Shami Tonny'
};
</script>

<style>
body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
  background: linear-gradient(135deg, #000000, #111111, #1a1a1a);
  color: white;
}

#app {
  min-height: 100vh;
}

nav {
  background: #000000;
  padding: 15px;
  text-align: center;
  position: sticky;
  top: 0;
  z-index: 10;
}

nav a {
  color: white;
  text-decoration: none;
  margin: 15px;
  font-weight: bold;
  transition: 0.3s;
}

nav a:hover {
  color: #888;
}

header {
  padding: 60px 20px;
  max-width: 1200px;
  margin: 0 auto;
}

.hero {
  display: grid;
  grid-template-columns: 1fr minmax(280px, 340px);
  gap: 32px;
  align-items: center;
}

.hero-text {
  animation: fadeInUp 0.9s ease forwards;
}

header h1 {
  font-size: 44px;
  margin: 0 0 16px;
}

header p {
  color: #ccc;
  line-height: 1.7;
  max-width: 600px;
}

.profile-card {
  padding: 16px;
  background: transparent;
  animation: fadeInUp 0.9s ease forwards;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

.profile-photo {
  position: relative;
  width: 280px;
  height: 280px;
  border-radius: 50%;
  overflow: visible;
  animation: glowPulse 3s ease-in-out infinite;
}

.profile-photo img {
  width: 100%;
  height: 100%;
  display: block;
  object-fit: cover;
  border-radius: 50%;
  transition: transform 0.8s ease;
  box-shadow: 0 0 20px rgba(81, 232, 106, 0.6), 0 0 40px rgba(81, 232, 106, 0.3), inset 0 0 20px rgba(81, 232, 106, 0.15);
}

.profile-card:hover .profile-photo img {
  transform: scale(1.05);
}

.profile-details {
  padding: 20px;
  background: rgba(255, 255, 255, 0.06);
  border: 1px solid rgba(81, 232, 106, 0.25);
  border-radius: 16px;
  width: 100%;
  box-shadow: 0 8px 32px rgba(81, 232, 106, 0.1);
}

.profile-details p,
.profile-details li {
  margin: 0 0 14px;
  color: #ddd;
  font-size: 14px;
}

.profile-details ul {
  list-style: disc inside;
  margin: 0;
  padding: 0;
  color: #ccc;
  font-size: 13px;
}

.profile-details li {
  margin-bottom: 8px;
}

.status-badge {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  background: rgba(81, 232, 106, 0.12);
  color: #9efeac;
  border: 1px solid rgba(81, 232, 106, 0.2);
  border-radius: 999px;
  padding: 10px 16px;
  font-weight: 700;
  box-shadow: 0 0 24px rgba(81, 232, 106, 0.15);
  animation: pulse 2.5s ease-in-out infinite;
}

.status-badge span {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: #51e86a;
  box-shadow: 0 0 12px rgba(81, 232, 106, 0.75);
}

section {
  padding: 40px 20px;
  margin: 20px auto;
  max-width: calc(100% - 40px);
  width: 1100px;
  box-sizing: border-box;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.02) 0%, rgba(81, 232, 106, 0.03) 100%);
  border: 1px solid rgba(81, 232, 106, 0.15);
  border-left: 3px solid rgba(81, 232, 106, 0.4);
  border-radius: 12px;
  opacity: 0;
  transform: translateY(24px);
  animation: fadeInUp 0.9s ease forwards;
  backdrop-filter: blur(10px);
  transition: all 0.4s ease;
}

@media (max-width: 1200px) {
  section {
    width: 100%;
    max-width: calc(100% - 40px);
    padding: 40px 20px;
  }
}

section:hover {
  border-left-color: rgba(81, 232, 106, 0.8);
  box-shadow: 0 12px 48px rgba(81, 232, 106, 0.08);
}

section:nth-of-type(1) { animation-delay: 0.1s; }
section:nth-of-type(2) { animation-delay: 0.2s; }
section:nth-of-type(3) { animation-delay: 0.3s; }
section:nth-of-type(4) { animation-delay: 0.35s; }
section:nth-of-type(5) { animation-delay: 0.4s; }
section:nth-of-type(6) { animation-delay: 0.45s; }
section:nth-of-type(7) { animation-delay: 0.5s; }
section:nth-of-type(8) { animation-delay: 0.55s; }

h2 {
  background: linear-gradient(90deg, #9efeac 0%, rgba(158, 254, 172, 0.6) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  border-bottom: 2px solid rgba(81, 232, 106, 0.3);
  padding-bottom: 14px;
  margin-bottom: 20px;
  font-size: 24px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1px;
  position: relative;
}

h2::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 60px;
  height: 2px;
  background: linear-gradient(90deg, #51e86a, transparent);
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
  line-height: 2;
}

li {
  padding-left: 24px;
  position: relative;
  color: #ddd;
  transition: all 0.3s ease;
}

li:hover {
  color: #9efeac;
  transform: translateX(6px);
}

li::before {
  content: '▸';
  position: absolute;
  left: 0;
  color: #51e86a;
  font-size: 18px;
  font-weight: bold;
}

.projects-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 24px;
  padding: 12px 0;
}

.project-card {
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.04) 0%, rgba(81, 232, 106, 0.02) 100%);
  padding: 28px;
  border-radius: 14px;
  border: 1px solid rgba(81, 232, 106, 0.2);
  transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  position: relative;
  overflow: hidden;
  cursor: pointer;
}

.project-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(81, 232, 106, 0.15), transparent);
  transition: left 0.5s ease;
  z-index: 1;
}

.project-card:hover::before {
  left: 100%;
}

.project-card:hover {
  transform: translateY(-8px) scale(1.02);
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.08) 0%, rgba(81, 232, 106, 0.06) 100%);
  border-color: rgba(81, 232, 106, 0.5);
  box-shadow: 0 20px 60px rgba(81, 232, 106, 0.15), 0 0 40px rgba(81, 232, 106, 0.1);
}

.project-card h3 {
  margin: 0 0 12px 0;
  font-size: 20px;
  color: #9efeac;
  transition: all 0.3s ease;
  position: relative;
  z-index: 2;
}

.project-card:hover h3 {
  color: #51e86a;
  text-shadow: 0 0 20px rgba(81, 232, 106, 0.5);
}

.project-card p {
  color: #bbb;
  font-size: 14px;
  line-height: 1.6;
  margin: 0;
  position: relative;
  z-index: 2;
  transition: color 0.3s ease;
}

.project-card:hover p {
  color: #ddd;
}

.languages-table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}

.languages-table thead {
  background: rgba(81, 232, 106, 0.15);
}

.languages-table th,
.languages-table td {
  padding: 16px;
  text-align: left;
  color: #ddd;
}

.languages-table th {
  border-bottom: 2px solid rgba(81, 232, 106, 0.3);
  color: #9efeac;
  font-weight: 700;
}

.languages-table td {
  border-bottom: 1px solid rgba(81, 232, 106, 0.2);
}

.languages-table tr:hover {
  background: rgba(81, 232, 106, 0.05);
}

.language-icon-cell {
  text-align: center;
  padding: 12px 16px !important;
}

.language-icon {
  width: 40px;
  height: 40px;
  object-fit: contain;
  filter: brightness(1.1);
}

footer {
  background: linear-gradient(135deg, #0a0a0a, #151515);
  padding: 50px 20px;
  color: white;
  font-size: 14px;
  border-top: 1px solid rgba(81, 232, 106, 0.2);
  box-shadow: inset 0 2px 20px rgba(81, 232, 106, 0.05);
}

.footer-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  max-width: 1200px;
  margin: 0 auto;
}

.footer-left,
.footer-center,
.footer-right {
  flex: 1;
  min-width: 200px;
  margin: 10px 0;
}

.footer-left h3,
.footer-center h3,
.footer-right h3 {
  margin-bottom: 10px;
  border-bottom: 1px solid #444;
  padding-bottom: 5px;
}

.social-icons a {
  margin-right: 10px;
  display: inline-block;
  transition: transform 0.3s;
}

.social-icons a:hover {
  transform: scale(1.2);
}

.social-icons img {
  width: 24px;
  height: 24px;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(24px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes pulse {
  0%,
  100% {
    transform: scale(1);
    box-shadow: 0 0 24px rgba(81, 232, 106, 0.15);
  }
  50% {
    transform: scale(1.02);
    box-shadow: 0 0 32px rgba(81, 232, 106, 0.22);
  }
}

@keyframes glowPulse {
  0%,
  100% {
    filter: drop-shadow(0 0 20px rgba(81, 232, 106, 0.5));
  }
  50% {
    filter: drop-shadow(0 0 40px rgba(81, 232, 106, 0.8));
  }
}

@media (max-width: 860px) {
  .hero {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .profile-card {
    max-width: 340px;
    margin: 0 auto;
  }

  .profile-details {
    text-align: left;
  }
}

@media (max-width: 560px) {
  nav {
    padding: 12px;
  }

  nav a {
    display: block;
    margin: 8px 0;
  }
}
</style>
