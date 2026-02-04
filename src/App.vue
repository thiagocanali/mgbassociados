<template>
  <div class="site-wrapper">
    <header class="main-header">
      <div class="logo">MGB <span class="gold">Associados</span></div>
      <button class="menu-trigger" @click="menuOpen = true">
        <span class="dot"></span>
        <span class="dot"></span>
        <span class="dot"></span>
      </button>
    </header>

    <div :class="['nav-overlay', { 'active': menuOpen }]">
      <button class="close-menu" @click="menuOpen = false">&times;</button>
      <nav class="nav-container">
        <a href="#home" @click="menuOpen = false">Início</a>
        <a href="#sobre" @click="menuOpen = false">Quem Somos</a>
        <a href="#areas" @click="menuOpen = false">Áreas de Atuação</a>
        <a href="#equipe" @click="menuOpen = false">Equipe</a>
        <a href="#contato" @click="menuOpen = false" class="btn-menu">Entre em Contato</a>
      </nav>
    </div>

    <section id="home" class="hero">
      <video autoplay muted loop playsinline class="hero-video">
        <source src="https://assets.mixkit.co/videos/preview/mixkit-justice-scales-in-a-lawyers-office-39745-large.mp4"
          type="video/mp4">
      </video>
      <div class="hero-overlay"></div>
      <div class="hero-content">
        <h2 class="subtitle">MGB & ASSOCIADOS</h2>
        <h1>Garantimos 100% de <span class="gold">Dedicação</span></h1>
        <p>Equipe totalmente capaz para lidar com seu caso da melhor forma.</p>
        <a href="#contato" class="cta-gold">Falar com Especialista</a>
      </div>
    </section>

    <section id="sobre" class="section-padding bg-white">
      <div class="container grid-2">
        <div class="about-img-box">
          <img src="https://images.unsplash.com/photo-1589829545856-d10d557cf95f?auto=format&fit=crop&q=80&w=800"
            alt="MGB Associados">
          <div class="experience-badge">
            <span class="num">18</span>
            <span class="txt">Anos de<br>Experiência</span>
          </div>
        </div>
        <div class="about-text">
          <span class="top-line"></span>
          <h2 class="section-label">Quem Somos</h2>
          <h3>Especialistas em <span class="gold">Direito Previdenciário</span></h3>
          <p>Identificamos e valorizamos os indivíduos e suas histórias. Desde 2012, as advogadas Camila e Adriana unem
            expertises para reconhecer os direitos de nossos clientes.</p>
          <div class="features">
            <div class="feat">✓ Atendimento Presencial ou Virtual</div>
            <div class="feat">✓ Foco em Excelência e Ética</div>
          </div>
        </div>
      </div>
    </section>

    <section id="areas" class="section-padding bg-gray">
      <div class="container">
        <div class="section-title text-center">
          <h2 class="font-serif text-3xl mb-4">Áreas de Atuação</h2>
          <p>Veja algumas áreas em que atuamos com expertise</p>
        </div>
        <div class="areas-grid">
          <div v-for="area in areas" :key="area.title" class="area-card">
            <div class="area-icon">⚖</div>
            <h3>{{ area.title }}</h3>
            <p>{{ area.desc }}</p>
            <a href="#contato" class="area-link">Consulte-nos</a>
          </div>
        </div>
      </div>
    </section>

    <section id="equipe" class="section-padding bg-white">
      <div class="container">
        <div class="section-title text-center">
          <h2 class="font-serif text-3xl mb-8">Nossa Equipe</h2>
        </div>
        <div class="team-grid">
          <div v-for="member in team" :key="member.name" class="team-card">
            <div class="member-photo-container">
              <img :src="member.image" :alt="member.name" class="member-img">
            </div>
            <h4>{{ member.name }}</h4>
            <span>{{ member.role }}</span>
          </div>
        </div>
      </div>
    </section>

    <footer id="contato" class="main-footer">
      <div class="container footer-grid">
        <div class="footer-info">
          <div class="logo">MGB <span class="gold">Associados</span></div>
          <p>Equipe coesa interessada em prover o melhor atendimento do começo ao fim.</p>
        </div>
        <div class="footer-contact">
          <h4>Contato</h4>
          <p>📍 Av. Conselheiro Nébias, 754 - Santos/SP</p>
          <p>📞 (13) 3223-6447</p>
          <p>✉️ contato@mgbassociados.com.br</p>
        </div>
        <div class="footer-hours">
          <h4>Horários</h4>
          <p>Seg - Sex: 8h às 18h</p>
          <p>Sábado: 9h às 12h</p>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2026 MGB Associados - Todos os direitos reservados.</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const menuOpen = ref(false);

const areas = [
  { title: 'Previdenciária', desc: 'Atuação na fase administrativa e judicial para concessão e revisão de benefícios.' },
  { title: 'Civil', desc: 'Normas referentes às relações jurídicas e obrigações de natureza privada.' },
  { title: 'Criminal', desc: 'Ampla atuação abrangendo crimes contra o patrimônio, vida e honra.' },
  { title: 'Tributário', desc: 'Planejamento tributário e defesa em esferas administrativas.' },
  { title: 'Família', desc: 'Especialistas dedicados às causas familiares e sucessões.' },
  { title: 'Administrativo', desc: 'Suporte em sindicâncias e defesas de processos administrativos.' }
];

const team = [
  {
    name: 'Camila Marques',
    role: 'Advogada Previdenciária',
    image: 'src/assets/fotos/CamilaMarques.jpg' // Caminho da foto na pasta public
  },
  {
    name: 'Adriana Barreto',
    role: 'Advogada Civil',
    image: 'src/assets/fotos/AdrianaBarreto.jpg'
  },
  {
    name: 'William Lima',
    role: 'Estagiário',
    image: 'src/assets/fotos/WilliamLima.jpg'
  },
  {
    name: 'Iasmim V. Cardoso',
    role: 'Estagiária',
    image: 'src/assets/fotos/IasmimCardoso.jpg'
  },
  {
    name: 'Bianca Requena',
    role: 'Estagiária',
    image: 'src/assets/fotos/BiancaRequena.jpg'
  }
];
</script>

<style scoped>
/* ESTILOS GERAIS */
.site-wrapper {
  color: #fff;
  background: #0a0a0a;
  font-family: 'Montserrat', sans-serif;
  line-height: 1.6;
  overflow-x: hidden;
}

.gold {
  color: #c5a059;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 25px;
}

.font-serif {
  font-family: 'Playfair Display', serif;
}

.section-padding {
  padding: 80px 0;
}

.bg-white {
  background: #fff;
  color: #333;
}

.bg-gray {
  background: #f9f9f9;
  color: #333;
}

/* HEADER */
.main-header {
  position: fixed;
  top: 0;
  width: 100%;
  height: 75px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 5%;
  z-index: 100;
  background: rgba(0, 0, 0, 0.85);
  backdrop-filter: blur(8px);
  border-bottom: 1px solid rgba(197, 160, 89, 0.2);
  box-sizing: border-box;
}

.logo {
  font-family: 'Playfair Display', serif;
  font-size: 1.3rem;
  font-weight: bold;
  letter-spacing: 1px;
}

/* MENU OVERLAY CENTRALIZADO */
.nav-overlay {
  position: fixed;
  top: 0;
  right: -100%;
  width: 100%;
  height: 100vh;
  background: #0d0d0d;
  z-index: 200;
  transition: 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  display: flex;
  justify-content: center;
  align-items: center;
}

.nav-overlay.active {
  right: 0;
}

.nav-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.nav-container a {
  color: #fff;
  text-decoration: none;
  font-size: 1.8rem;
  margin: 15px 0;
  font-family: 'Playfair Display', serif;
  transition: 0.3s;
}

.nav-container a:hover {
  color: #c5a059;
}

.close-menu {
  position: absolute;
  top: 20px;
  right: 30px;
  font-size: 3rem;
  background: none;
  border: none;
  color: #c5a059;
  cursor: pointer;
}

/* HERO */
.hero {
  position: relative;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 0 20px;
}

.hero-video {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -1;
}

.hero-overlay {
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.6);
}

.hero-content {
  position: relative;
  z-index: 10;
  width: 100%;
}

.hero-content h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.2rem, 10vw, 4rem);
  margin: 15px 0;
  font-weight: 700;
}

/* QUEM SOMOS */
.grid-2 {
  display: flex;
  flex-direction: column;
  gap: 40px;
}

.about-img-box {
  position: relative;
}

.about-img-box img {
  width: 100%;
  border-radius: 4px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.experience-badge {
  position: absolute;
  bottom: 15px;
  right: 15px;
  background: #c5a059;
  color: #000;
  padding: 15px;
  text-align: center;
  font-weight: bold;
}

/* EQUIPE & ÁREAS */
.areas-grid,
.team-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 25px;
  margin-top: 40px;
}

.area-card {
  padding: 30px;
  border: 1px solid #eee;
  background: #fdfdfd;
  border-left: 4px solid #c5a059;
}

.team-card {
  text-align: center;
  background: #fdfdfd;
  padding-bottom: 20px;
  border-bottom: 2px solid #eee;
}

.member-photo-container {
  width: 100%;
  height: 350px;
  overflow: hidden;
  margin-bottom: 15px;
  border-radius: 4px;
  background: #f0f0f0;
  /* Fundo caso a imagem demore a carregar */
}

.member-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  /* Faz a foto preencher o espaço sem distorcer */
  filter: grayscale(100%);
  /* Efeito PB elegante */
  transition: 0.5s ease;
}

.team-card:hover .member-img {
  filter: grayscale(0%);
  /* A foto ganha cor quando passa o mouse */
  transform: scale(1.05);
  /* Zoom suave */
}

/* FOOTER CENTRALIZADO NO MOBILE */
.main-footer {
  padding: 60px 0 0;
  background: #0a0a0a;
  color: #fff;
}

.footer-grid {
  display: flex;
  flex-direction: column;
  gap: 40px;
  text-align: center;
}

.footer-bottom {
  margin-top: 40px;
  padding: 30px 20px;
  border-top: 1px solid #222;
  text-align: center;
  width: 100%;
  box-sizing: border-box;
}

.footer-bottom p {
  font-size: 0.85rem;
  color: #666;
  margin: 0;
}

/* DESKTOP AJUSTES */
@media (min-width: 768px) {
  .grid-2 {
    flex-direction: row;
    align-items: center;
  }

  .about-text,
  .about-img-box {
    flex: 1;
  }

  .areas-grid {
    grid-template-columns: repeat(3, 1fr);
  }

  .team-grid {
    grid-template-columns: repeat(3, 1fr);
  }

  .footer-grid {
    flex-direction: row;
    justify-content: space-between;
    text-align: left;
  }

  .nav-overlay {
    max-width: 400px;
  }
}

.cta-gold {
  display: inline-block;
  margin-top: 20px;
  padding: 16px 32px;
  border: 1px solid #c5a059;
  color: #c5a059;
  text-decoration: none;
  text-transform: uppercase;
  font-size: 0.8rem;
  letter-spacing: 2px;
  font-weight: bold;
}
</style>