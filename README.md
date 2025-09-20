<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Rao Computers — Modern Dark One Page</title>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;500;700&family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <div class="brand"><a href="#home">Rao<span>Computers</span></a></div>
    <nav>
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#services">Services</a>
      <!-- <a href="#gallery">Gallery</a> -->
      <a href="#contact" class="cta">Contact</a>
    </nav>
  </header>

  <!-- Hero -->
  <section class="hero" id="home">
    <div class="hero-bg">
      <canvas id="heroParticles"></canvas>
      <div class="gradient-overlay"></div>
    </div>
    <div class="hero-content container">
      <h1 class="hero-title">we do work which is <span id="typed"></span></h1>
      <p class="hero-lead">Rao Computers: Excellence in digital solutions, goverment schemes, photocopy documents, fill electric bils and many more.</p>
      <div class="hero-info-block">
        <div class="hero-stat-experience-box">
          <strong>5+ years</strong>
          <span>Experience</span>
        </div>
        <div class="hero-cafe-line">
          All internet cafe related work is done here
        </div>
        <div class="hero-contact">
          <span><i class="fas fa-envelope"></i> raocsc@gmail.com</span><br>
          <span><i class="fas fa-phone"></i> 9813154132</span>
        </div>
      </div>
    </div>
  </section>

  <!-- Features -->
  <section class="features container" id="about">
    <div class="feature-card tilt">
      <i class="fas fa-brain fa-2x"></i>
      <h3>Strategy</h3>
      <p>Data-driven plans to scale revenue.</p>
    </div>
    <div class="feature-card tilt">
      <i class="fas fa-layer-group fa-2x"></i>
      <h3>Design</h3>
      <p>Brand & UI/UX that converts.</p>
    </div>
    <div class="feature-card tilt">
      <i class="fas fa-code fa-2x"></i>
      <h3>Build</h3>
      <p>Fast & maintainable web apps.</p>
    </div>
  </section>

  <!-- Services -->
  <section class="preview container" id="services">
    <h2>Featured Services</h2>
    <div class="services-grid">
      <div class="service-card tilt gradient-glow">
        <i class="fas fa-chart-line"></i>
        <h4>Business Consulting</h4>
        <p>Growth strategy and execution.</p>
      </div>
      <div class="service-card tilt gradient-glow">
        <i class="fas fa-palette"></i>
        <h4>Brand & Design</h4>
        <p>Visual identity and UI/UX.</p>
      </div>
      <div class="service-card tilt gradient-glow">
        <i class="fas fa-shield-alt"></i>
        <h4>Web & App Dev</h4>
        <p>Secure scalable applications.</p>
      </div>
    </div>
  </section>

  <!-- CTA strip -->
  <section class="cta-strip">
    <div class="container">
      <h3>Call on 9813154132 to know more</h3>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact">
    <div class="container contact-grid">
      <div class="contact-info">
        <h2>Contact Us</h2>
        <p>Email: raocsc@gmail.com</p>
        <p>Phone: 9813154132</p>
        <p>Address: near police choki, mahendargarh, 123021, haryana</p>
        <div class="map-placeholder">[Google Map]</div>
        <div class="socials">
          <i class="fab fa-facebook"></i> <i class="fab fa-instagram"></i> <i class="fab fa-linkedin"></i>
        </div>
      </div>
      <form class="contact-form" id="contactForm">
        <input type="text" name="name" placeholder="Full name" required />
        <input type="email" name="email" placeholder="Email address" required />
        <input type="text" name="subject" placeholder="Subject" />
        <textarea name="message" placeholder="Message" rows="5" required></textarea>
        <button class="btn btn-primary" type="submit">Send Message</button>
      </form>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <div class="container footer-grid">
      <div>
        <h4>Rao Computers</h4>
        <p>Digital services with clarity and measurable results.</p>
      </div>
      <div>
        <h4>Contact</h4>
        <p>Email: raocsc@gmail.com<br/>Phone: 9813154132<br/>Address: near police choki, mahendargarh, 123021, haryana</p>
      </div>
      <div>
        <h4>Follow</h4>
        <p class="socials"><i class="fab fa-facebook"></i> <i class="fab fa-instagram"></i> <i class="fab fa-linkedin"></i></p>
      </div>
    </div>
    <div class="copyright">© <span id="year"></span> Rao Computers — All rights reserved</div>
  </footer>

  <!-- Offer Modal -->
  <div id="offerModal" class="modal">
    <div class="modal-box">
      <button class="modal-close" aria-label="close">&times;</button>
      <h3>Limited Time Offer</h3>
      <p>Claim 15% off your first project — limited slots.</p>
      <form id="offerForm">
        <input type="text" name="name" placeholder="Your name" required />
        <input type="email" name="email" placeholder="Email" required />
        <button class="btn btn-primary" type="submit">Claim</button>
      </form>
    </div>
  </div>

  <script>
    // Year
    document.getElementById('year').textContent = new Date().getFullYear();

    // Typed effect - animates "perfect" and "visible" after the static tagline, now repeats SLOWER
    (function(){
      var el = document.getElementById('typed');
      if(!el) return;
      var words = ['perfect','visible'];
      var i = 0, idx = 0, forward = true;
      function tick() {
        el.textContent = words[i].slice(0, idx);
        if (forward) {
          if (idx < words[i].length) {
            idx++;
            setTimeout(tick, 120);
          } else {
            setTimeout(function() {
              forward = false;
              tick();
            }, 1200); // SLOWER after fully typed
          }
        } else {
          if (idx > 0) {
            idx--;
            setTimeout(tick, 70);
          } else {
            setTimeout(function() {
              forward = true;
              i = (i + 1) % words.length;
              tick();
            }, 700); // SLOWER after deleted
          }
        }
      }
      tick();
    })();

    // Particles
    (function(){const c=document.getElementById('heroParticles');if(!c)return;const ctx=c.getContext('2d');function resize(){c.width=c.clientWidth;c.height=c.clientHeight;}window.addEventListener('resize',resize);resize();const pts=[];const colors=['rgba(124,58,237,0.9)','rgba(6,182,212,0.9)','rgba(245,158,11,0.95)','rgba(255,255,255,0.8)'];for(let i=0;i<60;i++){pts.push({x:Math.random()*c.width,y:Math.random()*c.height,r:Math.random()*2+0.6,vx:(Math.random()-0.5)*0.6,vy:(Math.random()-0.5)*0.6,c:colors[Math.floor(Math.random()*colors.length)]});}function loop(){ctx.clearRect(0,0,c.width,c.height);for(const p of pts){p.x+=p.vx;p.y+=p.vy;if(p.x<0)p.x=c.width;if(p.x>c.width)p.x=0;if(p.y<0)p.y=c.height;if(p.y>c.height)p.y=0;ctx.beginPath();ctx.fillStyle=p.c;ctx.globalAlpha=0.85;ctx.arc(p.x,p.y,p.r,0,Math.PI*2);ctx.fill();}requestAnimationFrame(loop);}loop();})();

    // Tilt
    document.querySelectorAll('.tilt').forEach(function(el){el.addEventListener('mousemove',function(e){var r=el.getBoundingClientRect();var x=(e.clientX-r.left)/r.width;var y=(e.clientY-r.top)/r.height;var rx=(y-0.5)*10;var ry=(x-0.5)*-10;el.style.transform="perspective(900px) rotateX("+rx+"deg) rotateY("+ry+"deg) translateZ(6px)";});el.addEventListener('mouseleave',function(){el.style.transform='';});});

    // Offer modal
    var offerModal=document.getElementById('offerModal');
    document.getElementById('openOffer').addEventListener('click',function(e){e.preventDefault();offerModal.style.display='flex';});
    offerModal.querySelector('.modal-close').addEventListener('click',function(){offerModal.style.display='none';});
    offerModal.addEventListener('click',function(e){if(e.target===offerModal)offerModal.style.display='none';});
    offerModal.querySelector('#offerForm').addEventListener('submit',function(e){e.preventDefault();alert('Offer claimed — we will contact you!');offerModal.style.display='none';});

    // Contact form
    document.getElementById('contactForm').addEventListener('submit',function(e){e.preventDefault();alert('Thanks — message received.');this.reset();});
  </script>
</body>
</html>
