<!DOCTYPE html>
<html>

<head>

    <title>Kausik JARVIS 🤖</title>

    <style>

        body {
            background-color: black;
            color: white;
            text-align: center;
            font-family: Arial, sans-serif;
            padding-top: 50px;
        }

        h1 {
            color: cyan;
            font-size: 45px;
            text-shadow: 0 0 20px cyan;
        }

        #status {
            font-size: 20px;
            color: cyan;
            margin: 30px;
        }

        /* JARVIS REACTOR */

        .reactor {
            width: 180px;
            height: 180px;
            border: 5px solid cyan;
            border-radius: 50%;
            margin: auto;

            box-shadow:
                0 0 20px cyan,
                0 0 50px cyan,
                0 0 100px cyan;

            display: flex;
            justify-content: center;
            align-items: center;

            animation: glow 2s infinite alternate;
        }

        .core {
            width: 80px;
            height: 80px;
            background-color: cyan;
            border-radius: 50%;

            box-shadow:
                0 0 20px cyan,
                0 0 50px cyan;

            animation: pulse 1s infinite alternate;
        }

        @keyframes glow {

            from {
                box-shadow:
                    0 0 20px cyan,
                    0 0 40px cyan;
            }

            to {
                box-shadow:
                    0 0 40px cyan,
                    0 0 100px cyan;
            }

        }

        @keyframes pulse {

            from {
                transform: scale(0.8);
            }

            to {
                transform: scale(1.1);
            }

        }

        /* BUTTON */

        button {

            background-color: cyan;
            color: black;

            border: none;

            padding: 15px 30px;

            border-radius: 30px;

            font-size: 18px;

            font-weight: bold;

            box-shadow: 0 0 20px cyan;

            cursor: pointer;
        }

        button:active {
            transform: scale(0.95);
        }

    </style>

</head>


<body>

    <div class="reactor">
        <div class="core"></div>
    </div>

    <h1>JARVIS 🤖</h1>

    <p id="status">
        SYSTEM ONLINE
    </p>

    <button onclick="startJarvis()">
        🎙️ ACTIVATE JARVIS
    </button>


    <script>

        /* JARVIS VOICE */

        function speak(text) {

            let voice = new SpeechSynthesisUtterance(text);

            voice.rate = 1;
            voice.pitch = 1;

            speechSynthesis.speak(voice);

        }


        /* START LISTENING */

        function startJarvis() {

            let recognition = new webkitSpeechRecognition();

            recognition.lang = "en-US";

            recognition.start();


            document.getElementById("status").innerHTML =
                "🎙️ LISTENING...";


            recognition.onresult = function(event) {

                let command =
                    event.results[0][0].transcript.toLowerCase();


                document.getElementById("status").innerHTML =
                    "You said: " + command;


                /* HELLO */

                if (command.includes("hello")) {

                    speak("Hello boss. How can I help you?");

                }


                /* TIME */

                else if (command.includes("time")) {

                    let time =
                        new Date().toLocaleTimeString();

                    speak("The time is " + time);

                }


                /* DATE */

                else if (command.includes("date")) {

                    let date =
                        new Date().toLocaleDateString();

                    speak("Today's date is " + date);

                }


                /* YOUTUBE */

                else if (command.includes("youtube")) {

                    speak("Opening YouTube.");

                    window.open(
                        "https://www.youtube.com"
                    );

                }


                /* GOOGLE */

                else if (command.includes("google")) {

                    speak("Opening Google.");

                    window.open(
                        "https://www.google.com"
                    );

                }


                /* GITHUB */

                else if (command.includes("github")) {

                    speak("Opening GitHub.");

                    window.open(
                        "https://github.com"
                    );

                }


                /* JARVIS */

                else if (command.includes("jarvis")) {

                    speak("Yes boss. I am listening.");

                }


                /* UNKNOWN COMMAND */

                else {

                    speak(
                        "Sorry boss. I don't understand that command yet."
                    );

                }

            };


            recognition.onerror = function() {

                document.getElementById("status").innerHTML =
                    "❌ Could not hear you.";

                speak("Sorry boss. I could not hear you.");

            };

        }

    </script>

</body>

</html>
