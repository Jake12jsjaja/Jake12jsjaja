<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Babagsak Ka Ba?</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        button {
            padding: 10px 20px;
            font-size: 18px;
            margin: 10px;
            cursor: pointer;
        }
        #noBtn {
            position: relative;
        }
        #deserve {
            display: none;
            font-size: 50px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Babagsak ka ba?</h1>
    <button id="yesBtn">Yes</button>
    <button id="noBtn">No</button>

    <!-- Hidden "Deserve" message -->
    <div id="deserve">DESERVE!</div>

    <!-- Laughing sound -->
    <audio id="laughSound">
        <source src="https://www.soundjay.com/human/laugh-01.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>

    <script>
        const noBtn = document.getElementById("noBtn");
        const yesBtn = document.getElementById("yesBtn");
        const deserveMsg = document.getElementById("deserve");
        const laughSound = document.getElementById("laughSound");

        // "No" button moves when hovered over
        noBtn.addEventListener("mouseover", function() {
            const x = Math.random() * window.innerWidth - noBtn.offsetWidth;
            const y = Math.random() * window.innerHeight - noBtn.offsetHeight;
            noBtn.style.position = "absolute";
            noBtn.style.left = `${x}px`;
            noBtn.style.top = `${y}px`;
        });

        // "Yes" button shows "Deserve" and plays laughing sound
        yesBtn.addEventListener("click", function() {
            document.body.innerHTML = ''; // Clear the page
            deserveMsg.style.display = "block"; // Show "Deserve" message
            document.body.appendChild(deserveMsg); // Add "Deserve" to the page
            laughSound.play(); // Play laughing sound
        });
    </script>
</body>
</html>
