# TO-MY-SPECIAL-SUPPORTERS
 INDEX.html
 <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>You Are Special</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>

  <div class="background-decor">
    <div class="css-flower flower1"></div>
    <div class="css-flower flower2"></div>
    <div class="css-flower flower3"></div>
    <div class="css-flower flower4"></div>

    <div class="bg-heart heart1"></div>
    <div class="bg-heart heart2"></div>
    <div class="bg-heart heart3"></div>
    <div class="bg-heart heart4"></div>
  </div>

  <div class="container">
    <div class="letter-box" onclick="openLetter()">
      <div class="lid"></div>
      <div class="envelope"></div>
      <div class="message" id="message">
        <p>You are special 💖</p>
      </div>
    </div>

    <div class="floating-hearts" id="hearts">
      <div class="heart"></div>
      <div class="heart"></div>
      <div class="heart"></div>
      <div class="heart"></div>
      <div class="heart"></div>
    </div>
  </div>
style.css
/* Container and background decor */
body, html {
    margin: 0;
    padding: 0;
    height: 100%;
    font-family: 'Segoe UI', sans-serif;
    background-color: #ffe4f1;
    overflow: hidden;
  }
  
  .container {
    position: relative;
    z-index: 1;
  }
  
  /* Background floating elements */
  .background-decor {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
    z-index: 0;
  }
  
  .css-flower {
    position: absolute;
    width: 15px;
    height: 15px;
    background: radial-gradient(circle, #ffc0cb, #ff69b4);
    border-radius: 50%;
    opacity: 0.6;
    animation: floatFlower 14s infinite ease-in-out;
    box-shadow: 0 0 0 5px rgba(255,182,193,0.2),
                5px 5px 0 0 rgba(255,192,203,0.1),
                -5px -5px 0 0 rgba(255,105,180,0.1);
  }
  
  .flower1 { left: 10%; animation-delay: 0s; }
  .flower2 { left: 35%; animation-delay: 3s; }
  .flower3 { left: 65%; animation-delay: 5s; }
  .flower4 { left: 85%; animation-delay: 8s; }
  
  @keyframes floatFlower {
    0% { bottom: -30px; transform: rotate(0deg) translateX(0); opacity: 0.2; }
    50% { transform: rotate(180deg) translateX(20px); opacity: 0.6; }
    100% { bottom: 110%; transform: rotate(360deg) translateX(-20px); opacity: 0; }
  }
  
  .bg-heart {
    position: absolute;
    width: 20px;
    height: 20px;
    background-color: rgba(255, 105, 180, 0.5);
    transform: rotate(45deg);
    animation: floatHeartBg 12s infinite linear;
    border-radius: 10%;
  }
  
  .bg-heart::before,
  .bg-heart::after {
    content: '';
    position: absolute;
    width: 20px;
    height: 20px;
    background-color: rgba(255, 105, 180, 0.5);
    border-radius: 50%;
  }
  .bg-heart::before { top: -10px; left: 0; }
  .bg-heart::after { top: 0; left: -10px; }
  
  .heart1 { left: 20%; animation-delay: 0s; }
  .heart2 { left: 50%; animation-delay: 4s; }
  .heart3 { left: 70%; animation-delay: 7s; }
  .heart4 { left: 85%; animation-delay: 9s; }
  
  @keyframes floatHeartBg {
    0% { bottom: -30px; opacity: 0.3; transform: rotate(45deg) scale(1); }
    50% { opacity: 0.7; transform: rotate(45deg) scale(1.2); }
    100% { bottom: 110%; opacity: 0; transform: rotate(45deg) scale(1); }
  }
  
  /* Letter box styling */
  .letter-box {
    position: relative;
    width: 220px;
    height: 160px;
    margin: 100px auto;
    cursor: pointer;
    transition: transform 0.5s ease;
    transform-style: preserve-3d;
    perspective: 800px;
    z-index: 2;
  }
  
  .letter-box .lid {
    position: absolute;
    top: 0;
    width: 100%;
    height: 60px;
    background: linear-gradient(145deg, #ff85a2, #ff5d89);
    border-radius: 12px 12px 0 0;
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    transition: transform 0.6s ease;
    transform-origin: top center;
    z-index: 2;
  }
  
  .letter-box .envelope {
    position: absolute;
    top: 60px;
    width: 100%;
    height: 100px;
    background: linear-gradient(to bottom, #fff0f5, #ffe4ec);
    border-radius: 0 0 12px 12px;
    box-shadow: inset 0 4px 6px rgba(255, 182, 193, 0.2), 0 4px 10px rgba(0,0,0,0.1);
    border-top: 2px solid #ff9cb4;
  }
  .letter-box .envelope::after {
    content: '';
    position: absolute;
    top: 0;
    left: 10px;
    width: 100%;
    height: 100%;
    background: linear-gradient(45deg, rgba(255,255,255,0.4), transparent);
    transform: skewX(-20deg);
    animation: shine 3s infinite;
    pointer-events: none;
    border-radius: 0 0 12px 12px;
  }
  
  @keyframes shine {
    0% { transform: translateX(-100%) skewX(-20deg); }
    50% { transform: translateX(100%) skewX(-20deg); }
    100% { transform: translateX(-100%) skewX(-20deg); }
  }
  
  .letter-box .message {
    position: absolute;
    top: 20px;
    left: 0;
    width: 100%;
    padding: 10px;
    text-align: center;
    font-size: 18px;
    font-weight: bold;
    color: #d6336c;
    display: none;
    background-color: rgba(255, 255, 255, 0.95);
    border-radius: 10px;
    animation: fadeIn 1s ease forwards;
    z-index: 3;
  }
  
  .letter-box.open .lid {
    transform: rotateX(-120deg);
  }
  
  @keyframes fadeIn {
    from { transform: scale(0.8); opacity: 0; }
    to { transform: scale(1); opacity: 1; }
  }
  
  /* Floating hearts on open */
  .floating-hearts {
    position: absolute;
    top: 0;
    left: 50%;
    width: 200px;
    height: 200px;
    transform: translateX(-50%);
    pointer-events: none;
    display: flex;
    justify-content: space-around;
    opacity: 0;
    transition: opacity 0.5s ease;
  }
  
  .floating-hearts.float {
    animation: floatUp 2s ease-in-out forwards;
    opacity: 1;
  }
  
  .floating-hearts .heart {
    width: 20px;
    height: 20px;
    background-color: #ff5c8d;
    transform: rotate(45deg);
    position: relative;
    animation: floatHeart 2s infinite;
    opacity: 0.8;
  }
  
  .floating-hearts .heart::before,
  .floating-hearts .heart::after {
    content: '';
    width: 20px;
    height: 20px;
    background-color: #ff5c8d;
    border-radius: 50%;
    position: absolute;
  }
  
  .floating-hearts .heart::before {
    top: -10px;
    left: 0;
  }
  .floating-hearts .heart::after {
    left: -10px;
    top: 0;
  }
  
  @keyframes floatUp {
    from { transform: translateX(-50%) translateY(0); opacity: 0; }
    to { transform: translateX(-50%) translateY(-100px); opacity: 1; }
  }
  
  @keyframes floatHeart {
    0%, 100% { transform: translateY(0) rotate(45deg); }
    50% { transform: translateY(-10px) rotate(45deg); }
  }
  
  <script>
    function openLetter() {
      const letterBox = document.querySelector('.letter-box');
      const message = document.getElementById('message');
      const hearts = document.getElementById('hearts');

      if (!letterBox.classList.contains('open')) {
        letterBox.classList.add('open');
        message.style.display = 'block';
        hearts.classList.add('float');
      }
    }
  </script>

</body>
</html>

