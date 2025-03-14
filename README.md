<!DOCTYPE html>
<html>
<head>
<title>Graffiti DJ GC Banner</title>
<style>
  @font-face {
    font-family: 'Graffiti';
    src: url('your-graffiti-font.ttf') format('truetype'); /* Replace with your font file */
  }

  .banner {
    background-color: red;
    color: black;
    text-align: center;
    padding: 30px;
    font-family: 'Graffiti', sans-serif; /* Use the graffiti font */
    font-size: 72px; /* Increased font size for graffiti */
    font-weight: normal; /* Graffiti fonts often don't need bold */
    letter-spacing: 5px;
    text-transform: uppercase;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    position: relative;
    overflow: hidden;
  }

  .banner span {
    display: inline-block;
    animation: letterAnimation 1s infinite alternate;
    position: relative;
  }

  @keyframes letterAnimation {
    0% { transform: translateY(0); }
    100% { transform: translateY(-10px); }
  }
</style>
</head>
<body>

<div class="banner">
  <span>D</span><span>J</span> <span>G</span><span>C</span>
</div>

</body>
</html>
