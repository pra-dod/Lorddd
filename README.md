<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>A Special Message</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;600;700&family=Poppins:wght@300;400;500;600&display=swap');

    body {
      margin: 0;
      padding: 0;
      overflow-x: hidden;
    }

    .heart {
      animation: heartbeat 1.5s ease-in-out infinite;
    }
    @keyframes heartbeat {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.1); }
    }

    .fade-in {
      animation: fadeIn 1s ease-in;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .firework {
      position: absolute;
      width: 4px;
      height: 4px;
      border-radius: 50%;
      animation: firework 1s ease-out forwards;
      pointer-events: none;
    }
    @keyframes firework {
      0% { transform: scale(1); opacity: 1; }
      100% { transform: scale(20); opacity: 0; }
    }

    .rose {
      position: absolute;
      font-size: 2rem;
      animation: fall 5s linear infinite;
      pointer-events: none;
    }
    @keyframes fall {
      0% { transform: translateY(-100vh) rotate(0deg); opacity: 1; }
      100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
    }

    .romantic-bg {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      min-height: 100vh;
    }

    .card-glow {
      box-shadow: 0 20px 40px rgba(0,0,0,0.1), 0 0 20px rgba(255,255,255,0.1);
    }

    .pulse-button {
      animation: pulse 2s infinite;
    }
    @keyframes pulse {
      0% { box-shadow: 0 0 0 0 rgba(236, 72, 153, 0.7); }
      70% { box-shadow: 0 0 0 10px rgba(236, 72, 153, 0); }
      100% { box-shadow: 0 0 0 0 rgba(236, 72, 153, 0); }
    }

    .shake {
      animation: shake 0.5s ease-in-out;
    }
    @keyframes shake {
      0%, 100% { transform: translateX(0); }
      25% { transform: translateX(-5px); }
      75% { transform: translateX(5px); }
    }
  </style>
</head>

<body class="romantic-bg">
  <!-- Background Music -->
  <audio id="backgroundMusic" loop>
    <source src="https://ik.imagekit.io/uj3ix8qln/Diamond_Ni_x_To_Mathare_Tikili_Bhala_Laguni___Odia_Song_Status___Odia_Romantic_Status(360p).mp3?updatedAt=1754300361325" type="audio/mpeg">
    Your browser does not support the audio element.
  </audio>

  <!-- Name Entry Screen -->
  <div id="nameEntry" class="min-h-screen flex items-center justify-center p-4">
    <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-8 max-w-md w-full card-glow fade-in">
      <div class="text-center">
        <div class="text-6xl mb-4 heart">💖</div>
        <h1 class="text-3xl font-bold text-gray-800 mb-2" style="font-family: 'Dancing Script', cursive;">Something Special Awaits</h1>
        <p class="text-gray-600 mb-6" style="font-family: 'Poppins', sans-serif;">Please enter your name to continue</p>
        <input type="text" id="nameInput" placeholder="Your beautiful name..."
          class="w-full px-4 py-3 border-2 border-pink-200 rounded-xl focus:border-pink-400 focus:outline-none text-center text-lg mb-4"
          style="font-family: 'Poppins', sans-serif;">
        <button onclick="checkName()"
          class="w-full bg-gradient-to-r from-pink-400 to-purple-500 text-white py-3 rounded-xl font-semibold hover:from-pink-500 hover:to-purple-600 transition-all duration-300 pulse-button"
          style="font-family: 'Poppins', sans-serif;">
          Enter ✨
        </button>
        <div id="errorMessage" class="text-red-500 mt-4 hidden"></div>
      </div>
    </div>
  </div>

  <!-- Welcome Screen -->
  <div id="welcomeScreen" class="min-h-screen flex items-center justify-center p-4 hidden">
    <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-8 max-w-2xl w-full card-glow fade-in text-center">
      <div class="text-6xl mb-6">🌹</div>
      <h1 class="text-4xl font-bold text-gray-800 mb-4" style="font-family: 'Dancing Script', cursive;">
        Welcome, KRISHNA✨ 💕
      </h1>
      <p class="text-lg text-gray-700 mb-8 leading-relaxed" style="font-family: 'Poppins', sans-serif;">
        I don’t know how you do it, but life feeling softer after seeing you.  TODAY,I want to shar something...
      </p>
      <button onclick="showShayari()"
        class="bg-gradient-to-r from-rose-400 to-pink-500 text-white px-8 py-3 rounded-xl font-semibold hover:from-rose-500 hover:to-pink-600 transition-all duration-300"
        style="font-family: 'Poppins', sans-serif;">
        Continue....💖
      </button>
    </div>
  </div>

  <!-- Shayari Screen -->
  <div id="shayariScreen" class="min-h-screen flex items-center justify-center p-4 hidden">
    <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-8 max-w-3xl w-full card-glow fade-in">
      <div class="text-center mb-8">
        <div class="flex justify-center space-x-4 mb-6">
          <div class="w-20 h-20 bg-gradient-to-br from-pink-300 to-purple-400 rounded-full flex items-center justify-center text-2xl">🌸</div>
          <div class="w-20 h-20 bg-gradient-to-br from-purple-300 to-pink-400 rounded-full flex items-center justify-center text-2xl">💕</div>
          <div class="w-20 h-20 bg-gradient-to-br from-pink-300 to-purple-400 rounded-full flex items-center justify-center text-2xl">🌺</div>
        </div>
        <h2 class="text-3xl font-bold text-gray-800 mb-6" style="font-family: 'Dancing Script', cursive;">
          प्रिए 
        </h2>
        <div class="bg-gradient-to-r from-pink-50 to-purple-50 p-6 rounded-2xl mb-8">
          <p class="text-xl text-gray-700 leading-relaxed italic" style="font-family: 'Dancing Script', cursive;">
            "आप चाँद है, मैं आपका दीवाना,
आपके रोशनी में खो जाता हूँ हर दिन पुराना।"<br>
            "पहली नजर में ही हुआ दीवाना,आपके हर अदा पे ये दिल हुआ नादान",<br>
            "क्रिष्णा,क्या आप बनेंगे इस नादान का सहारा"
          </p>
        </div>
        <p class="text-lg text-gray-700 mb-8" style="font-family: 'Poppins', sans-serif;">
          Every heart seeks grace; mine found you. Will you be my swan?
        </p>
        <div class="flex justify-center space-x-6">
          <button onclick="handleYes()"
            class="bg-gradient-to-r from-green-400 to-emerald-500 text-white px-8 py-4 rounded-xl font-semibold hover:from-green-500 hover:to-emerald-600 transition-all duration-300 text-lg"
            style="font-family: 'Poppins', sans-serif;">
            Yes! 💚
          </button>
          <button onclick="handleNo()"
            class="bg-gradient-to-r from-red-400 to-pink-500 text-white px-8 py-4 rounded-xl font-semibold hover:from-red-500 hover:to-pink-600 transition-all duration-300 text-lg"
            style="font-family: 'Poppins', sans-serif;">
            No 💔
          </button>
        </div>
      </div>
    </div>
  </div>

  <!-- Yes Screen -->
  <div id="yesScreen" class="min-h-screen flex items-center justify-center p-4 hidden">
    <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-8 max-w-2xl w-full card-glow fade-in text-center">
      <div class="text-8xl mb-6">🎉</div>
      <h1 class="text-4xl font-bold text-green-600 mb-4" style="font-family: 'Dancing Script', cursive;">
        YES! 💕
      </h1>
      <p class="text-lg text-gray-700 mb-6" style="font-family: 'Poppins', sans-serif;">
        Krishna,...
        From now I will be the luckiest man to gaze the moon more near 😊...
      </p>
      <div class="text-6xl mb-4">👩‍❤️‍👨</div>
      <p class="text-xl text-pink-600 font-semibold" style="font-family: 'Dancing Script', cursive;">
        Forever Yours ❤️
      </p>
    </div>
  </div>

  <!-- No Screen -->
  <div id="noScreen" class="min-h-screen flex items-center justify-center p-4 hidden">
    <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-8 max-w-2xl w-full card-glow fade-in text-center">
      <div class="text-6xl mb-6">🥺</div>
      <h1 class="text-3xl font-bold text-gray-800 mb-4" style="font-family: 'Dancing Script', cursive;">
        Please Reconsider, Krishna 💕
      </h1>
      <div class="space-y-4 mb-8">
        <p class="text-lg text-gray-700" style="font-family: 'Poppins', sans-serif;">
        </p>
        <p class="text-lg text-gray-700" style="font-family: 'Poppins', sans-serif;">
I don’t just love you, Krishna — I’m incomplete without you. Be my swan, my forever, my everything. Say yes, and make me the happiest man alive....🤧
        </p>
        <p class="text-lg text-gray-700" style="font-family: 'Poppins', sans-serif;">
          
        </p>
        <p class="text-lg text-gray-700" style="font-family: 'Poppins', sans-serif;">
          
        </p>
      </div>
      <button onclick="showShayari()"
        class="bg-gradient-to-r from-purple-400 to-pink-500 text-white px-8 py-3 rounded-xl font-semibold hover:from-purple-500 hover:to-pink-600 transition-all duration-300"
        style="font-family: 'Poppins', sans-serif;">
        Give me Another Chance? 💕
      </button>
    </div>
  </div>

  <script>
    function checkName() {
      const nameInput = document.getElementById('nameInput');
      const errorMessage = document.getElementById('errorMessage');
      const audio = document.getElementById('backgroundMusic');
      const name = nameInput.value.trim().toLowerCase();

      if (name === '') {
        showError('Please enter your name first! 💕');
        return;
      }

      if (name === 'krishna') {
        document.getElementById('nameEntry').classList.add('hidden');
        document.getElementById('welcomeScreen').classList.remove('hidden');
        errorMessage.classList.add('hidden');
        audio.play(); // start music after name entry
      } else {
        showError('Sorry, this is not for you 💔');
        nameInput.classList.add('shake');
        setTimeout(() => nameInput.classList.remove('shake'), 500);
      }
    }

    function showError(message) {
      const errorMessage = document.getElementById('errorMessage');
      errorMessage.textContent = message;
      errorMessage.classList.remove('hidden');
    }

    function showShayari() {
      document.getElementById('welcomeScreen').classList.add('hidden');
      document.getElementById('noScreen').classList.add('hidden');
      document.getElementById('shayariScreen').classList.remove('hidden');
    }

    function handleYes() {
      document.getElementById('shayariScreen').classList.add('hidden');
      document.getElementById('yesScreen').classList.remove('hidden');
      createFireworks();
      createFallingRoses();
    }

    function handleNo() {
      document.getElementById('shayariScreen').classList.add('hidden');
      document.getElementById('noScreen').classList.remove('hidden');
    }

    function createFireworks() {
      const colors = ['#ff6b6b', '#4ecdc4', '#45b7d1', '#96ceb4', '#ffeaa7', '#dda0dd'];
      for (let i = 0; i < 15; i++) {
        setTimeout(() => {
          const firework = document.createElement('div');
          firework.className = 'firework';
          firework.style.left = Math.random() * window.innerWidth + 'px';
          firework.style.top = Math.random() * window.innerHeight + 'px';
          firework.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
          document.body.appendChild(firework);
          setTimeout(() => firework.remove(), 1000);
        }, i * 200);
      }
    }

    function createFallingRoses() {
      for (let i = 0; i < 20; i++) {
        setTimeout(() => {
          const rose = document.createElement('div');
          rose.className = 'rose';
          rose.textContent = '🌹';
          rose.style.left = Math.random() * window.innerWidth + 'px';
          rose.style.animationDelay = Math.random() * 2 + 's';
          rose.style.animationDuration = (Math.random() * 3 + 2) + 's';
          document.body.appendChild(rose);
          setTimeout(() => rose.remove(), 6000);
        }, i * 300);
      }
    }

    // Allow Enter key to submit
    document.getElementById('nameInput').addEventListener('keypress', function(e) {
      if (e.key === 'Enter') checkName();
    });
  </script>
</body>
</html>
