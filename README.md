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

