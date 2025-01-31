<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Surat untuk Sandra</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(135deg, #ff758c, #ff7eb3);
            font-family: 'Courier New', monospace;
            text-align: center;
            color: #fff;
            flex-direction: column;
        }

        .envelope-container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .envelope {
            width: 220px;
            height: 150px;
            background: #e74c3c;
            position: relative;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 10px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .envelope:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }

        .flap {
            width: 0;
            height: 0;
            border-left: 110px solid transparent;
            border-right: 110px solid transparent;
            border-bottom: 80px solid #c0392b;
            position: absolute;
            top: -40px;
            left: 0;
        }

        .letter {
            width: 180px;
            height: 100px;
            background: white;
            position: absolute;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 16px;
            font-weight: bold;
            color: #333;
            border-radius: 5px;
        }

        .container {
            background: rgba(255, 255, 255, 0.3);
            padding: 25px;
            border-radius: 10px;
            backdrop-filter: blur(10px);
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
            max-width: 90%;
            width: 350px;
            text-align: center;
            display: none;
            animation: fadeIn 1s ease-in-out;
        }

        h1 {
            font-size: 22px;
            margin-bottom: 15px;
            color: white;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
        }

        #text {
            font-size: 18px;
            white-space: pre-line;
            overflow: hidden;
            display: inline-block;
            text-align: left;
            color: white;
            line-height: 1.5;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }
    </style>
</head>
<body>
    <div id="envelopeContainer" class="envelope-container">
        <div id="envelope" class="envelope" onclick="openLetter()">
            <div class="flap"></div>
            <div class="letter">Klik untuk membuka</div>
        </div>
    </div>

    <div id="letterContainer" class="container">
        <h1>Untuk Sandra 🤍</h1>
        <p id="text"></p>
    </div>

    <script>
        function openLetter() {
            document.getElementById("envelopeContainer").style.display = "none";
            document.getElementById("letterContainer").style.display = "block";
            typeWriter();
        }

        const message = `hai sandra,\n\nada sesuatu yang pengen aku sampaikan ke kamu...\n
bukan tentang seberapa spesial kamu di mataku,\nkamu pasti udah tau itu.\n\n
ini cuma tentang betapa nyamannya aku bisa ada di sekitar kamu,\ndan betapa bersyukurnya aku karena bisa mengenal kamu.\n\n
tetap jadi sandra yang apa adanya, ya. 🤍`;

        let index = 0;
        function typeWriter() {
            if (index < message.length) {
                document.getElementById("text").textContent += message.charAt(index);
                index++;
                setTimeout(typeWriter, 50);
            }
        }
    </script>
</body>
</html>
