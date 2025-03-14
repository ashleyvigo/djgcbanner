<!DOCTYPE html>
<html>
<head>
<title>DJ GC Animated Banner</title>
<style>
.banner {
    width: 300px;
    height: 100px;
    background-color: #111;
    position: relative;
    overflow: hidden;
}

/* Equalizer Bars */
.bar {
    width: 8px;
    position: absolute;
    bottom: 0;
    animation: pulseBar 1.2s ease-in-out infinite alternate, colorCycleBar 3s linear infinite; /* Combined animations */
}

@keyframes pulseBar {
    0% {
        height: 15px;
    }
    100% {
        height: 60px; /* Max Height */
    }
}

@keyframes colorCycleBar {
    0% {
        background-color: #00ff00; /* Green */
    }
    33% {
        background-color: #ffff00; /* Yellow */
    }
    66% {
        background-color: #ff00ff; /* Magenta */
    }
    100% {
        background-color: #00ff00; /* Back to Green */
    }
}

/* Text */
.text {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-family: sans-serif;
    font-size: 30px;
    color: white;
    z-index: 1; /* Ensure text is on top of bars and flash */
    white-space: nowrap;
    animation: wobble 2s ease-in-out infinite alternate;
}

@keyframes wobble {
    0% {
        transform: translate(-50%, -50%) rotate(-2deg);
    }
    100% {
        transform: translate(-50%, -50%) rotate(2deg);
    }
}

/* Multiple Background Flashes */
.flash {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(255, 255, 0, 0.8);  /* Yellow, semi-transparent */
    opacity: 0;
    animation: multipleFlashes 2s steps(4) infinite;  /* steps(4) creates 4 distinct flashes */
    z-index: 0; /*  Behind text */
}

@keyframes multipleFlashes {
    0% { opacity: 0; }
    25% { opacity: 1; }
    50% { opacity: 0; }
    75% { opacity: 1; }
    100% { opacity: 0; }
}
</style>
</head>
<body>

<div class="banner" id="banner">
    <div class="flash"></div>
    <div class="text">DJ GC</div>
</div>

<script>
const banner = document.getElementById('banner');
const numBars = 25; //Number of bars
const barSpacing = 12; //Spacing between the bars

for (let i = 0; i < numBars; i++) {
    const bar = document.createElement('div');
    bar.classList.add('bar');
    bar.style.left = (i * barSpacing) + 'px';
    bar.style.animationDelay = Math.random() * 1.2 + 's'; // Vary bar animation
    banner.appendChild(bar);
}
</script>

</body>
</html>
