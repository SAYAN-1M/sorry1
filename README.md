<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sorry </title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    .gradient-background {
      background: rgb(255, 208, 229);
      background: linear-gradient(180deg, rgba(255, 208, 229, 1) 0%, rgba(255, 232, 242, 1) 36%, rgba(255, 255, 255, 1) 100%);
    }

    .bounce2 {
      animation: bounce2 2s ease infinite;
    }

    @keyframes bounce2 {
      0%, 20%, 50%, 80%, 100% {
        transform: translateY(0);
      }
      40% {
        transform: translateY(-20px);
      }
      60% {
        transform: translateY(-10px);
      }
    }
  </style>
</head>
<body class="gradient-background">
  <div class="flex items-center justify-center h-screen">
    <div class="flex flex-col items-center p-4">
      <img id="imageDisplay" src="image2.gif" alt="Cute kitten with flowers" class="rounded-md h-[300px]" style="object-fit: cover;" />
      <h2 id="valentineQuestion" class="text-4xl font-bold italic text-[#bd1e59] my-4">Sorry Please forgive Me :-) !!</h2>
      <div class="flex gap-4 pt-[20px] items-center" id="responseButtons">
        <button id="yesButton"
          class="bounce2 inline-flex items-center justify-center whitespace-nowrap rounded-md text-[20px] font-medium disabled:pointer-events-none disabled:opacity-50 hover:bg-green-400 min-h-12 min-w-[75px] px-4 py-2 bg-green-500 text-white transition">
          Yes
        </button>   
        <button id="noButton"
          class="inline-flex items-center justify-center whitespace-nowrap rounded-md text-[20px] font-medium transition disabled:pointer-events-none disabled:opacity-50 hover:bg-red-700 h-12 min-w-[75px] w-auto px-4 py-2 bg-red-500 text-white">
          No
        </button>
      </div>
    </div>
  </div>

  <script type="module">
    import confetti from 'https://cdn.skypack.dev/canvas-confetti';
    const yesButton = document.getElementById('yesButton');
    const noButton = document.getElementById('noButton');
    const imageDisplay = document.getElementById('imageDisplay');
    const valentineQuestion = document.getElementById('valentineQuestion');
    const responseButtons = document.getElementById('responseButtons');
  
    let noClickCount = 0;
    let buttonHeight = 48; 
    let buttonWidth = 80;
    let fontSize = 20; 
    const imagePaths = [
      "image1.gif",
      "image2.gif",
      "image3.gif",
      "image4.gif",
      "image5.gif",
      "image6.gif",
      "image7.gif"
    ];
  
    noButton.addEventListener('click', function() {
      if (noClickCount < 4) {
        noClickCount++;
        imageDisplay.src = imagePaths[noClickCount];
        buttonHeight == 35; 
        buttonWidth == 35;
        fontSize == 25; 
        yesButton.style.width = `${buttonWidth}px`;
        yesButton.style.fontSize = `${fontSize}px`; 
        if (noClickCount < 6) {
          noButton.textContent = ["Kaha na Nahi", "Are You Sure", "Please Dont do this", "NOOO", "I'm gonna cry..."][noClickCount];
        }
      }
    });
  
    yesButton.addEventListener('click', () => {
      imageDisplay.src = 'image7.gif'; 
      valentineQuestion.textContent = "Yayyy Thankyou !! :3"; 
      responseButtons.style.display = 'none'; 
      confetti(); 
    });
  </script>  
</body>
</html>
