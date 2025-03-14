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

.bar {
    width: 10px;
    background-color: #00ff00;
    position: absolute;
    bottom: 0;
    animation: pulseBar 1s ease-in-out infinite alternate;
}

@keyframes pulseBar {
    0% {
        height: 20px;
    }
    100% {
        height: 80px; /*Max Height*/
    }
}
</style>
</head>
<body>

<div class="banner" id="banner">
    <div style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); font-size: 30px; color: white;">DJ GC</div>
</div>

<script>
const banner = document.getElementById('banner');
const numBars = 20; // Number of equalizer bars
const barSpacing = 15;

for (let i = 0; i < numBars; i++) {
    const bar = document.createElement('div');
    bar.classList.add('bar');
    bar.style.left = (i * barSpacing) + 'px';
    bar.style.animationDelay = Math.random() * 1.5 + 's'; // Vary animation speed
    banner.appendChild(bar);
}
</script>

</body>
</html>
