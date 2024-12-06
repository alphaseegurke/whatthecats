<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ page.title }}</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        /* General Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            color: #fff;
            background: #0d0d0d;
            overflow-x: hidden;
        }

        h1 {
            font-size: 3rem;
            text-align: center;
            margin-top: 20px;
            color: #FFD700;
            text-shadow: 0 0 20px rgba(255, 215, 0, 0.5);
        }

        p {
            text-align: center;
            margin: 20px 0;
            font-size: 1.2rem;
            color: #bbb;
        }

        /* Buttons */
        .button-container {
            text-align: center;
            margin-top: 50px;
        }

        button {
            font-size: 1.3rem;
            padding: 15px 40px;
            margin: 15px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease-in-out;
            color: white;
            box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.3);
            outline: none;
        }

        #startButton {
            background: linear-gradient(135deg, #4CAF50, #2E7D32);
        }

        #startButton:hover {
            background: linear-gradient(135deg, #66BB6A, #388E3C);
            transform: scale(1.1);
        }

        #stopButton {
            background: linear-gradient(135deg, #F44336, #D32F2F);
        }

        #stopButton:hover {
            background: linear-gradient(135deg, #E57373, #C62828);
            transform: scale(1.1);
        }

        /* Status Display */
        #status {
            text-align: center;
            margin-top: 30px;
            font-size: 1.5rem;
            color: #FFD700;
            transition: color 0.3s ease;
        }

        /* Background Animation */
        .background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: radial-gradient(circle, #1a1a1a, #0d0d0d);
            overflow: hidden;
        }

        .circle {
            position: absolute;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            animation: float 8s infinite ease-in-out;
            mix-blend-mode: screen;
            pointer-events: none;
        }

        @keyframes float {
            0% {
                transform: translateY(0) scale(1);
            }
            50% {
                transform: translateY(-100px) scale(1.2);
            }
            100% {
                transform: translateY(0) scale(1);
            }
        }

        /* Random Circle Positions and Sizes */
        .circle:nth-child(1) {
            width: 120px;
            height: 120px;
            top: 10%;
            left: 15%;
            animation-duration: 9s;
        }

        .circle:nth-child(2) {
            width: 200px;
            height: 200px;
            top: 30%;
            left: 70%;
            animation-duration: 11s;
        }

        .circle:nth-child(3) {
            width: 80px;
            height: 80px;
            top: 60%;
            left: 35%;
            animation-duration: 13s;
        }

        .circle:nth-child(4) {
            width: 150px;
            height: 150px;
            top: 75%;
            left: 50%;
            animation-duration: 7s;
        }

        .circle:nth-child(5) {
            width: 250px;
            height: 250px;
            top: 15%;
            left: 85%;
            animation-duration: 14s;
        }
    </style>
</head>
<body>
    <div class="background">
        <div class="circle"></div>
        <div class="circle"></div>
        <div class="circle"></div>
        <div class="circle"></div>
        <div class="circle"></div>
    </div>

    <h1>Minecraft Server Control</h1>
    <p>Start or stop your server with just one click.</p>

    <div class="button-container">
        <button id="startButton">Start Server</button>
        <button id="stopButton">Stop Server</button>
    </div>

    <div id="status">Status: Offline</div>

    <script>
        const statusElement = document.getElementById('status');
        const startButton = document.getElementById('startButton');
        const stopButton = document.getElementById('stopButton');

        async function updateServerStatus(action) {
            try {
                const response = await fetch(`/api/server/${action}`, {
                    method: 'POST'
                });
                
                if (!response.ok) {
                    throw new Error('Server action failed');
                }

                const newStatus = action === 'start' ? 'Online' : 'Offline';
                const statusColor = action === 'start' ? '#4CAF50' : '#F44336';
                
                statusElement.textContent = `Status: ${newStatus}`;
                statusElement.style.color = statusColor;
            } catch (error) {
                console.error('Error:', error);
                alert(`Failed to ${action} the server. Please try again.`);
            }
        }

        startButton.addEventListener('click', () => updateServerStatus('start'));
        stopButton.addEventListener('click', () => updateServerStatus('stop'));
    </script>
</body>
</html>
