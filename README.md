<!DOCTYPE html>
<html>
<head>
<title>DJ GC Opening</title>
<style>
  @font-face {
    font-family: 'Graffiti';
    src: url('your-graffiti-font.ttf') format('truetype'); /* Replace with your font file */
  }

  body {
    margin: 0;
    overflow: hidden; /* Prevent scrollbars */
  }

  #video-background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover; /* Cover the entire screen */
    z-index: -2; /* Behind the banner */
  }

  .banner {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: white;
    text-align: center;
    font-family: 'Graffiti', sans-serif;
    font-size: 72px;
    font-weight: normal;
    letter-spacing: 5px;
    text-transform: uppercase;
    z-index: 1; /* Above the video */
    background-image: url('lightning.gif'); /* Lightning storm background */
    background-size: cover;
    padding: 20px;
    border-radius: 10px;
  }

  .banner span {
    display: inline-block;
    opacity: 0;
    transform: translateY(20px);
    animation: letterEntrance 1s forwards ease-out;
  }

  .banner span:nth-child(2) { animation-delay: 0.2s; }
  .banner span:nth-child(4) { animation-delay: 0.4s; }

  @keyframes letterEntrance {
    to { opacity: 1; transform: translateY(0); }
  }

  #particles-js {
    position: fixed;
    width: 100%;
    height: 100%;
    z-index: -1; /* Behind the banner, above video */
  }

  #smoke-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url('smoke.png'); /* Replace with your smoke texture */
    background-repeat: repeat;
    opacity: 0.5; /* Adjust opacity */
    pointer-events: none; /* Allow clicks to pass through */
    z-index: 0;
  }

</style>
</head>
<body>

  <video id="video-background" autoplay muted loop>
    <source src="your-video.mp4" type="video/mp4">
  </video>

  <div id="particles-js"></div>

  <div class="banner">
    <span>D</span><span>J</span> <span>G</span><span>C</span>
  </div>

  <div id="smoke-overlay"></div>

  <script src="particles.min.js"></script>
  <script>
    particlesJS('particles-js', {
      particles: {
        number: { value: 80, density: { enable: true, value_area: 800 } },
        color: { value: '#ffffff' },
        shape: { type: 'circle', stroke: { width: 0, color: '#000000' }, polygon: { nb_sides: 5 } },
        opacity: { value: 0.5, random: true, anim: { enable: false, speed: 1, opacity_min: 0.1, sync: false } },
        size: { value: 3, random: true, anim: { enable: false, speed: 40, size_min: 0.1, sync: false } },
        line_linked: { enable: true, distance: 150, color: '#ffffff', opacity: 0.4, width: 1 },
        move: { enable: true, speed: 3, direction: 'none', random: false, straight: false, out_mode: 'out', bounce: false, attract: { enable: false, rotateX: 600, rotateY: 1200 } }
      },
      interactivity: { detect_on: 'canvas', events: { onhover: { enable: true, mode: 'repulse' }, onclick: { enable: true, mode: 'push' }, resize: true }, modes: { grab: { distance: 400, line_linked: { opacity: 1 } }, bubble: { distance: 400, size: 40, duration: 2, opacity: 8, speed: 3 }, repulse: { distance: 200, duration: 0.4 }, push: { particles_nb: 4 }, remove: { particles_nb: 2 } } },
      retina_detect: true
    });
  </script>

</body>
</html>
