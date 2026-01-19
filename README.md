<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Best Sis Ever?</title>
    <style>
        body {
            background-color: #f3e5f5; /* Soft Lavender */
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow: hidden;
        }

.container {
            text-align: center;
            padding: 20px;
            z-index: 1;
        }

 .showering-hearts {
            width: 200px;
            height: auto;
            border-radius: 20px;
            margin-bottom: 20px;
        }

 h1 {
            color: #4a148c; /* Deep Purple */
            font-size: 2.2rem;
            margin-bottom: 30px;
        }

 .buttons {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
            flex-wrap: wrap;
        }

 .yes-button {
            background-color: #7b1fa2; /* Purple */
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1.2rem;
            font-weight: bold;
            transition: all 0.2s ease-out;
            box-shadow: 0 4px 15px rgba(123, 31, 162, 0.3);
        }

 .no-button {
            background-color: #9e9e9e; /* Grey */
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1.2rem;
            font-weight: bold;
        }

.hidden {
            display: none;
        }
    </style>
</head>
<body>

 <div id="question-view" class="container">
        <h1>Want to resubscribe  my brother subscription??</h1>
        <div class="buttons">
            <button class="yes-button" onclick="handleYesClick()">Of course! 🥰</button>
            <button class="no-button" onclick="handleNoClick()">mmH... ?</button>
        </div>
    </div>

<div id="success-view" class="container hidden">
        <h1 style="color: #4a148c;"> Let me take refund 😹🤣
        </h1>
    </div>

 <script>
        let messageIndex = 0;
        const messages = [
            "mmH... ?",
            "Are you really sure?",
            "But I'm your favorite brother!",
            "I'll share my snacks!",
            "I'll help with chores? (maybe)",
            "Don't be mean!",
            "Please? I'll be really nice!",
            "I'll tell Mom you're the best!",
            "Fine, I'll eat all the pizza myself...",
            "Just kidding! Say yes, sis! ✨"
        ];

        function handleNoClick() {
            const noButton = document.querySelector(".no-button");
            const yesButton = document.querySelector(".yes-button");
            
            noButton.textContent = messages[messageIndex];
            messageIndex = (messageIndex + 1) % messages.length;

            // Make the 'Yes' button grow
            const currentSize = parseFloat(window.getComputedStyle(yesButton).fontSize);
            yesButton.style.fontSize = ${currentSize * 1.4}px;
            
            const currentPadding = parseFloat(window.getComputedStyle(yesButton).padding);
            yesButton.style.padding = ${currentPadding * 1.1}px;
        }

        function handleYesClick() {
            document.getElementById("question-view").classList.add("hidden");
            document.getElementById("success-view").classList.remove("hidden");
            document.body.style.backgroundColor = "#e1bee7"; // Slightly darker purple
        }
    </script>
</body>
</html>
